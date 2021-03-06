세상
=====

.. index:: World()

.. note::

    ``World()`` 는 매우 특수한 함수로,
    저자는 정규 파이썬 관례를 따르지 않기로 하고,
    대문자로 시작되는 명칭을 부여했다.

**Home 1** 이 아닌 세상을 선택한다.
그리고 나서, 다음 프로그램을 **두번** 실행한다::

    World("Home 1")
    move()
    move()

처음 실행할 때, 세상이 **Home 1** 으로 변경된다는 정보를 리보그가 알려준다. 세상을 쳐다보면 확인할 수 있다.

두번째 실행할 때, **Home 1** 이 이미 선택되어 있기 때문에,
``World()`` 함수는 실제적으로 무시되고, 프로그램 나머지 부분이 실행된다.


프로그래밍 연습
--------------------

``World()`` 세상에 관해서 좀더 일러주기 전에,
이전에 작성했던 프로그램을 재방문한다.

.. topic:: 직접 작성한다! 이점이 중요하다.

    **Storm 1** 세상을 선택한다.
    리보그가 모든 낙엽을 모아서 쓰레기통에 담는 프로그램을 작성한다.
    작성한 프로그램에는 아마도 ``carries_object()`` 함수를
    사용하는 것이 필요하다.

.. hint::
    .. code-block:: py3

        from library import *
        think(0)

        def collect_leaves():
            while not wall_in_front():
                move()
                if object_here():
                    while object_here():
                        take()

        def throw_away():
            while not wall_in_front():
                move()
                if wall_in_front():
                    turn_right()
                    move()
                    while carries_object():
                        put()

        #----- 정의 끝

        collect_leaves()
        turn_around()
        throw_away()
        turn_around()
        move()

원격 세상 적재하기
-------------------------------------

**Storm 1** 세상을 면밀히 살펴보고,
낙엽이 있는 장소에 주목한다.

이제, **Storm 1** 에 흩어져 있는
모든 낙엽을 리보그가 주어서 쓰레기통에 담도록 작성한
프로그램 최상단에, 다음 코드 한줄을 추가한다::

    World("http://reeborg.ca/worlds/not_storm1.json")

[not_storm1 말미에 영문자 "l" 이 아니고, 숫자 "1" 임에 주의한다.] 프로그램을 한번 실행한다: 리보그가 세상이 적절히 잘 적재되었음을 일러줘야 한다. 모양은 이전에 살펴본 것과 통일해야 된다.

상단 세상명칭 선택자에 매우 긴 명칭( ``World()`` 함수에 인자로 사용됨)이 나온 것에 주목한다.

최상단 "World info" 버튼을 클릭한다. 세상에 대한 간략한 기술이 되어있는데, ``carries_object()`` 사용을 가정하지 않는다는 사실이 포함되어 있다.
이것은 무시하고, 프로그램을 실행한다. 발생한 일에 대해서 착실히 적어 놓는다.

원격 세상 다시 적재하기
------------------------------------

그래서, 작성한 프로그램은 정상 동작하는 것은 아니다.
이 문제를 어떻게 고치는지 곧 알게 된다.
그러는 동안에, 뭔가 다른 것을 했으면 한다.
프로그램 첫번째 줄을 다음과 같이 변경한다::

    World("http://reeborg.ca/worlds/not_storm1.json",
          "Not Storm 1")

``World()`` 함수에 두번째 인자를 추가했다.
편집기에서 한번에  세상을 보기에는 너무 길어서 이를 회피하고자, 다른 행에 두번째 인자를 넣었다.
파이썬은 ``(`` 시작 괄호를 함수 인자로 사용할 때,
닫는 괄호를 찾을 때까지 필요하면 다음 행까지 쭉 읽어 내려가고,
이 모든 것을 마치 한줄에 있었던 것처럼 처리한다.
**하지만**, 문자열은 쪼개지 않았음에 주목한다; 콤마 다음에 새줄에 작성했다. 그렇게 함으로써, 함수 인자는 해당 줄에 모두 위치하게 된다.

이제 다시 실행한다. 이렇게 바꾼다고, 작업하고 있던 문제가 해결된 것은 아니다. **하지만**, 상단을 살펴보면,
세상에 대한 명칭이 이전에 봤던 매우 긴 장문의 주소가 아니라
``Not Storm 1`` 으로 나온다.

작업 저장하기
--------------------------

로컬 컴퓨터에 파일 형태로 작성한 프로그램을 저장하고자 하면,
상단에 "Additional options" 과 "Save program to file" 을 클릭해서 저장한다.
나중에, 저장한 프로그램을 "Import program from file" 을 클릭해서 불러올 수 있다.

.. admonition:: 선생님께

    To do: 대신 ``permalinks`` 를 사용하는 방법을 설명한다.
