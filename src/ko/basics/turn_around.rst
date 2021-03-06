
돌아서다
===========

리보그가 우회전하는 것에 더해서, 몇번 리보그가 돌아섰을 *것이다.* 방향을 바꿔서 
리보그가 처음에 출발한 곳으로 다시 방향을 바꿨다. 다음과 같이 ``turn_around()`` 함수를 정의할 수 있다::

    def turn_around():
        turn_left()
        turn_left()

시도해 보기!

``turn_right()`` 로 되돌아가기
------------------------------------

``turn_right()`` 함수를 기억하는가? 다음에 함수가 있다::

    def turn_right():
        turn_left()
        turn_left()
        turn_left()

첫 두 명령어는 ``turn_around()`` 함수 정의와 동일함에 주목한다.
이런 일이 발생할 때, 3번째 규칙을 기억해야만 된다:

.. important::

    규칙 # 3
        프로그램을 작성할 때, 되풀이 반복하지 마세요.
        다시 말씀드립니다. **되풀이 반복하지 마세요!**

그래서, 일부 되풀이 반복되는 명령어가 있다. ``turn_right()`` 가 이미 충분히 단순하지만,
좋은 프로그래밍 습관은 반복되는 코드 부분을 간단한 함수로 교체하는 것이다. 그래서, ``turn_right()`` 함수를
다음과 같이 재작성해야만 된다::

    def turn_right():
        turn_around()
        turn_left()

이런 것에 숨은 생각은 다음과 같다. 함수가 짧아지면 질수록, 버그가 함수에 덜 있을 것같다는 것이다.
더 나아가, 잘 테스트된 버그없는 함수를 갖게 되면, 더 긴 함수를 장성할 때 함수를 원할 때마다 확실히 사용할 수 있다.
저자도 역자도 인정하지만, 이것은 정말 바보같은 예제다. 하지만, 이런 중요한 발상을 시연하는데 있어 이 지점에서
더 복잡한 예제를 갖고 있지는 않다.

.. topic:: 여러분 차례

    ``step_back()`` 함수를 정의해서 ``move()`` 함수 실행을 취소하게 한다.
    여러분은 다음을 작성해야 된다는 의미를 갖는다::

        # x, y 지점 어딘가에서 출발한다.
        move()
        step_back()
        # 동일한 지점으로 돌아온다.
        # 처음처럼 동일한 방향을 지향한다.

    작성한 함수를 확실히 테스트한다.

달리 할 수 없다는 느낌을 완전히 갖지 않는다면, 힌트를 사용하지 마시오!

.. hint::

   ``step_back()`` 함수를 정의하는데 있어 ``turn_around()`` 함수를 두번 사용할 수 있다.