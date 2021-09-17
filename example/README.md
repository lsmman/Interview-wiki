# example

* [Generator](#generator)

[뒤로](https://github.com/lsmman/Interview-wiki)

## Generator

[Generator(제네레이터)](https://docs.python.org/3/tutorial/classes.html#generators)는 제네레이터 함수가 호출될 때 반환되는 [iterator(이터레이터)](https://docs.python.org/3/tutorial/classes.html#iterators)의 일종이다. 제네레이터 함수는 일반적인 함수와 비슷하게 생겼지만 `yield 구문`을 사용해 데이터를 원하는 시점에 반환하고 처리를 다시 시작할 수 있다. 일반적인 함수는 진입점이 하나라면 제네레이터는 진입점이 여러개라고 생각할 수 있다. 이러한 특성때문에 제네레이터를 사용하면 원하는 시점에 원하는 데이터를 받을 수 있게된다.

### 예제

```python
>>> def generator():
...     yield 1
...     yield 'string'
...     yield True

>>> gen = generator()
>>> gen
<generator object generator at 0x10a47c678>
>>> next(gen)
1
>>> next(gen)
'string'
>>> next(gen)
True
>>> next(gen)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```

### 동작

1.  yield 문이 포함된 제네레이터 함수를 실행하면 제네레이터 객체가 반환되는데 이 때는 함수의 내용이 실행되지 않는다.
2.  `next()`라는 빌트인 메서드를 통해 제네레이터를 실행시킬 수 있으며 `next()` 메서드 내부적으로 iterator 를 인자로 받아 이터레이터의 `__next__()` 메서드를 실행시킨다.
3.  처음 `__next__()` 메서드를 호출하면 함수의 내용을 실행하다 yield 문을 만났을 때 처리를 중단한다.
4.  이 때 모든 local state 는 유지되는데 변수의 상태, 명령어 포인터, 내부 스택, 예외 처리 상태를 포함한다.
5.  그 후 제어권을 상위 컨텍스트로 양보(yield)하고 또 `__next__()`가 호출되면 제네레이터는 중단된 시점부터 다시 시작한다.

> yield 문의 값은 어떤 메서드를 통해 제네레이터가 다시 동작했는지에 따라 다른데, `__next__()`를 사용하면 None 이고 `send()`를 사용하면 메서드로 전달 된 값을 갖게되어 외부에서 데이터를 입력받을 수 있게 된다.
