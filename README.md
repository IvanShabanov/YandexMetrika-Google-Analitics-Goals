# YandexMetrikaGoal
Как правильно отправлять цели на Яандекс метрику

Javascript

function Goal(GOALNAME) {
	/* Проверим загрузился ли счетчик Yandex */
	if (typeof yaCounterXXXXXXX !== 'undefined') {
  		yaCounterXXXXXXX.reachGoal(GOALNAME);
	}
	/* Проверим загрузился ли Google Analytics */
	if (typeof ga !== 'undefined') {
  		ga('send', 'event', 'form', 'send', GOALNAME);
	}	
}
