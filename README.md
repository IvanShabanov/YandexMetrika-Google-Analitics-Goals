# YandexMetrikaGoal
Как правильно отправлять цели на Яандекс метрику

Javascript

	function Goal(GOALNAME) {
	    /* Проверим загрузился ли счетчик Yandex */
	    if (typeof yaCounterXXXXXXX !== 'undefined') {
		yaCounterXXXXXXX.reachGoal(GOALNAME);
	    }
	    if (typeof ym !== 'undefined') {
               ym(XXXXXXX, 'reachGoal', GOALNAME);
            };
	    /* Проверим загрузился ли Google Analytics */
	    if (typeof ga !== 'undefined') {
	    	/* 
		Для того чтобы это работало через Tag Manager надо 
		Переменные - Настройки Google Analitics - Расширенная конфигурация - Задать имя трекера 
		(поставить галочку) и отсавить имя трекера пустым
		*/
		ga('send', 'event', 'form', 'submit', GOALNAME);
	    }
	    if (typeof gtag !== 'undefined') {
		gtag('event', 'form_send', {
		    'event_category': 'form',
		    'event_action': 'submit',
		    'event_label': GOALNAME
		});
		/*
		gtag('event', <action>, {
		  'event_category': <category>,
		  'event_label': <label>,
		  'value': <value>
		});            
		*/
	    }
	}
