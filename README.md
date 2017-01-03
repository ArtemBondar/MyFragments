# MyFragments

Первым делом для фрагментов вызываются методы:
- V/Fragment1: onAttach
- V/Fragment1: onCreate
- V/Fragment1: onCreateView
- V/Fragment2: onAttach
- V/Fragment2: onCreate
- V/Fragment2: onCreateView
- V/MainActivity: onCreate
- V/Fragment1: onActivityCreated
- V/Fragment2: onActivityCreated
- V/Fragment1: onStart
- V/Fragment2: onStart
- V/MainActivity: onStart
- V/MainActivity: onResume
- V/Fragment1: onResume
- V/Fragment2: onResume

- onAttach – фрагмент прикреплен к Activity и получает ссылку на него. В дальнейшем мы всегда можем получить ссылку на Activity, вызвав метод getActivity().
- onCreate  - это аналог метода onCreate у Activity, но здесь мы пока не имеем доступа к UI-элементам
- onCreateView – здесь вы создаете View, который будет содержимым фрагмента, и отдаете его системе
- Далее срабатывают метод Activity – onCreate, после него метод фрагментов onActivityCreated – сообщает фрагменту о том, что Activity создано и можно работать с UI-элементами
- Далее метод Activity – onStart, после него onStart – аналогичен методу Activity, фрагмент виден пользователю
- Далее метод Activity – onResume, после него onResume - аналогичен методу Activity, фрагмент доступен для взаимодействия.

Жмем кнопку назад – закрываем приложение:
- V/Fragment1: onPause
- V/Fragment2: onPause
- V/MainActivity: onPause
- V/Fragment1: onStop
- V/Fragment2: onStop
- V/MainActivity: onStop
- V/Fragment1: onDestroyView
- V/Fragment1: onDestroy
- V/Fragment1: onDetach
- V/Fragment2: onDestroyView
- V/Fragment2: onDestroy
- V/Fragment2: onDetach
- V/MainActivity: onDestroy

- Сначала для фрагментов и Activity вызываются методы onPause и onStop. Это значит, что фрагменты и Activity более недоступны для взаимодействия, а потом не видны пользователю.
- Затем для фрагментов вызываются три метода по уничтожению:
- onDestroyView – сообщает нам, что View, которое мы создавали в onCreateView, более недоступно
- onDestroy – аналог метода onDestroy у Activity
- onDetach – фрагмент отсоединен от Activity
- И в конце вызывается метод onDestroy для Activity.
