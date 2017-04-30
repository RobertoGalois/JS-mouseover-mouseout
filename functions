/*
	fonction à executer lors d'un mouseover d'un élément donné
*/
function evOn(e)
{
	//on prend une variable élément et on lui stocke une ref à l'élément qui à la méthode de départ, et dont les enfants héritent
	var elementRef = e.currentTarget;

	//on prend une variable element et on lui stocke une ref vers l'élément QUE LA SOURIS A QUITTÉ pour entrer dans notre élément de départ
	var relatedTarget = e.relatedTarget;

	/*
		pour executer correctement le code du mouseover sans être parasité par le fait de quitter l'element de depart pour arriver sur des 
		elements enfants (qui héritent de l'évent de l'element de depart) ou inversement, et avoir des cycles entré-sortie en trop, 
		on doit checker que notre element quitté n'est NI notre element de départ (qui du coup pénètrerait dans un élément enfant), 
		NI un element enfant de notre élément de départ (qui du coup passerait d'un element enfant de l'élement de depart vers l'élement de depart)
		on ne doit executer le code QUE si on passe d'un élement frère ou parent à notre élément de départ
	*/

	//on va parser l'architecture DOM pour savoir si notre élément qui appelle l'event est un enfant de l'element de depart (et dont les enfants héritent)
	//TANT QUE: l'élément quitté n'est pas notre element de depart (en gros, relatedTarget prendra la valeur de l'élément de départ si l'élement quitté est d'un niveau <= élement de depart, 
	//cad qu'on est dans un passage d'élément de départ vers élément enfant ou inversement, et donc que le code ne doit pas être executé
	//OU qu'on arrive à <html> qui fait qu'on arrete le parsing (cas où l'élément quitté serait carrément au-delà de body)
	//OU qu'on arrive à notre <body> qui fait qu'on s'arrête dans le parsing et qu'on est sûr que l'element qui a appellé la méthode n'est pas un élément enfant du truc de départ 
	while(relatedTarget != elementRef && relatedTarget != document && relatedTarget.nodeName != 'BODY')
	{
		//on stocke dans notre variable une reference a l'element parent, on on remonte comme ça jusqu'à tomber
		//sur notre element de depart, si l'élément quitté etait un enfant de notre element de depart
		//ou sur <body> ou <html> sinon
		relatedTarget = relatedTarget.parentNode;
	}

	//s'il s'agit bien d'un passage d'un élément frère ou parent de l'élément de depart vers l'élément de depart
	if(relatedTarget != elementRef)
	{ 
     //trucs à faire si la souris passe d'un élément non enfant de l'élément de départ à l'élément de départ
	}
}

/*
	fonction à executer lors d'un mouseout du même élément donné
*/
function evOff(e)
{
	//on prend une variable élément et on lui stocke une ref à l'élément qui à la méthode de départ, et dont les enfants héritent
	var elementRef = e.currentTarget;

	//on prend une variable element et on lui stocke une ref vers l'élément QUE LA SOURIS PENETRE en quittant notre élément de départ
	var relatedTarget = e.relatedTarget;
	
	/*
		pour executer correctement le code du mouseout sans être parasité par le fait de quitter l'element de depart pour arriver sur des elements enfants ou inversement,
		et avoir des cycles entré-sortie en trop, 
		on doit checker que notre element quitté n'est NI notre element de départ, NI un enfant de notre élément de départ, afin de ne pas compter les passages 
		d'élément de départ vers enfant et inversement
	*/

	//on va parser l'architecture DOM pour savoir si notre élément qui appelle l'event est un enfant de l'element de depart (et dont les enfants héritent)
	//TANT QUE l'élément quitté n'est pas notre element de depart (en gros, relatedTarget prendra la valeur de l'élément de départ si l'élement pénétré est d'un niveau 
	//<= élement de depart, cad qu'on quitte un élément enfant de l'élément de départ pour pénétrer l'élément de départ ou inversement, auquel cas le code ne devra pas être executé
	//OU qu'on arrive à <html> qui fait qu'on arrete le parsing (cas où l'élément quitté serait carrément au-delà de body)
	//OU qu'on arrive à notre <body> qui fait qu'on s'arrête dans le parsing
	while(relatedTarget != elementDepart && relatedTarget != document && relatedTarget.nodeName != 'BODY')
	{
		//on stocke dans notre variable une reference a l'element parent, on on remonte comme ça jusqu'à tomber
		//sur notre element de depart, si l'élément pénétré est notre élément de départ ou un élément enfant de l'élément de depart
		//ou sur <body> ou <html> sinon
		relatedTarget = relatedTarget.parentNode;
	}

	//s'il s'agit bien d'un passage de l'élément de départ vers un élément frère ou parent de l'élément de départ
	if(relatedTarget != elementDepart)
	{
		 //Trucs a faire si la souris passe de l'élément de départ vers un autre élément non enfant.
	}
}
