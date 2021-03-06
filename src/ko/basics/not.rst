아니면 ... 참(true)!
========================

.. index:: ! not

리보그가 흥분했다. 비가 내리지 **않는다(not)** ; 눈도 내리지 **않는다(not).** 하지만,
밖에 나가서 장애물 경주를 연습할 수 없다.

왜냐고, 궁금하시죠? 리보가가 파이썬 키워드 **not** 을 여러분들이 배우기를 기다리고 있기 때문입니다.

부정할 시간.
--------------------

파이썬에서, 참(true)가 아닌 무언가를 ``not True`` 라고 작성하게 되면 ``False`` 와 동의어가 된다.
마찬가지로 ``not False`` 는 ``True`` 에 상응한다.

제발, 리보그를 행복하게 만들어 주세염
----------------------------------------

이미 리보그가 장애물을 넘을 수 있게 하는 프로그램을 작성했다;
프로그램 일부는 다음과 같이 작성된다:

.. code-block:: python

   def run_jump_or_finish ():
        if at_goal():
            # 무언가 수행한다.
        elif front_is_clear():
            # 무언가 수행한다.
        else:
            # 무언가 수행한다.

.. topic:: 시도해 보기!

    부정 키워드 ``not`` 과 그리고 **and** ``if/elif/else`` 다른 조합으로 세가지 다른 버젼의 프로그램을 
    재작성해서 리보그를 행복하게 하세요.

아래 세가지 코드 표본을 사용해야 하지만, ``not`` 키워드가 사용되는 곳 **그리고(and)** 각 코드 덩어리에 실제로 포함되는 것에
각별히 주의를 기울인다.

.. code-block:: python

   # first choice:

   def run_jump_or_finish ():
        if at_goal():
            # 무언가 수행한다.
        elif not front_is_clear():
            # 무언가 수행한다.
        else:
            # 무언가 수행한다.

   # second choice ... trickier

   def run_jump_or_finish ():
        if not at_goal():
            if front_is_clear():
                # 무언가 수행한다.
            else:
                # 무언가 수행한다.
        else:
            # 무언가 수행한다.

   # third choice:

   def run_jump_or_finish ():
        if not at_goal():
            if not front_is_clear():
                # 무언가 수행한다.
            else:
                # 무언가 수행한다.
        else:
            # 무언가 수행한다.

또다른 선택옵션
------------------

.. index:: wall_in_front()

여전히 동일한 목적을 달성하면서, ``if/elif/else`` 코드 덩어리에 나타나는 조건 순서를 변경할 수 있는 방법을 살펴봤다.
서로 다른 두 프로그래머가 동일한 최종 결과를 얻는데 다른 전략을 사용한다.
다른 프로그래머는 다르지만 상응하는 프로그램을 작성하는 다른 방식이 있다: 다른 함수를 사용해서.

``front_is_clear()`` 함수는 리보그에게 벽이 길을 막고 있는지 아닌지 일러준다.
아직 살펴보지는 않았지만, 미래 세상에서 가능한 **물가** , **벽돌 벽** , **담장** , 에도 동일한 작업을 수행한다.
벽에만 좀더 특수한 함수가 있다; ``wall_in_front()`` 로 불린다; 저자가 이 함수가 어떤 일을 할지 추측하는 것은 독자에게 맡긴다.

.. topic:: 시도해 보기!

    ``not front_is_clear()`` 와 상응하는 함수 대신에, 
    ``wall_in_front()`` 함수를 사용해서 프로그램을 작성한다.
