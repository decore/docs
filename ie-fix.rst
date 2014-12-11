IE fixes
========

Flex в IE (и не только)
-----------------------
.. code::

		flex: 1;
		-webkit-box-flex: 1 0 auto;
		-webkit-flex: 1 0 auto;
		-ms-box-flex: 1 0 auto;
		-ms-flex: 1 0 auto;
		-webkit-box-flex: 1;
		box-flex: 1 0 auto;
		flex: 1 0 auto; (для ie11 важно, чтоб эта строка была обязательно после flex: 1,
		 так как ie11 читает флекс без префикса, а flex:1 в нем работает не правильно)

		display: flex;
		display: -webkit-box
		display: -webkit-flex
		display: -ms-flexbox
		display: -ms-box
		display: box
		display: flexbox
		display: flex

		flex-direction: column;
		-webkit-box-orient: vertical
		-webkit-box-direction: normal
		-webkit-flex-direction: column
		-ms-box-orient: vertical
		-ms-flex-direction: column
		box-orient: vertical
		flex-direction: column

Исправление верстки для IE8
---------------------------
	
1).	Для респонзива respond.js ( работает только на сервере). 

.. code::

		<!--[if lt IE 9]>
			<script src="js/html5shiv.js" type="text/javascript"></script>
			<script src="js/respond.min.js"></script>
		<![endif]-->
Поместить в <head>

2).	Для работы скриптов на базе jQuiery использовать версию 1.11.1

.. code::

	<script src="js/jquery-1.11.1.min.js" type="text/javascript"></script>


https://github.com/owenversteeg/min Фреймворк для ie5