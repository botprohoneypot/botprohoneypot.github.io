# PHP Orientado a objetos

Estructura básica de una clase en PHP
```php
class unaClase{
	public $variable1;
	public static $string = 'Algo aqui';
	private $variable3;
	const UNA_CONSTANTE = 3.1416;
	
	public function unMetodo1($parametro1,$parametro2){
		echo "la variable 1 es ". $variable1 ." termina aqui";
	}
};
```

Para instanciar nuestra clase se hace de la siguiente forma:
```php
$unObjeto = new unaClase;
$unObjeto->unMetodo1('numero',1);
```

Para usar variables dentro de nuestra clase debemos crear nuestro `constructor`, en donde, están las variables que se van a usar dentro de nuestros métodos de la clase, este constructor es lo primero que se llama al ejecutar la clase, al instanciarla:
```php
class unaClase{
	public function __construct($parametro1, $parametro2){
		$this->uno = $parametro1;
		$this->dos = $parametro2;
	}
	public function unMetodo1(){
		echo $this->uno;
	}
};
```

También podemos agregar un `destructor` para finalizar los métodos o funciones que almacene nuestra clase, por ejemplo cerrar sesión o cerrar la conexión a una base de datos.

```php
class unaClase{
	public function __construct($parametro1, $parametro2){
		$this->uno = $parametro1;
		$this->dos = $parametro2;
	}
	public function unMetodo1(){
		echo $this->uno;
	}
	public function __destruct(){
		echo "esto es un destructor";
	}
};
```

Para usar las variables tipo constantes, públicas y estáticas fuera de nuestra clase usaremos lo siguiente:
```php
class unaClase{
	public $variable1;
	public static $string = 'Algo aqui';
	private $variable3;
	const UNA_CONSTANTE = 3.1416;
	
	public function unMetodo1($parametro1,$parametro2){
		echo "la variable 1 es ". $variable1 ." termina aqui";
	}
};

echo unaClase::$string;
echo unaClase::UNA_CONSTANTE;
```

Para usar la herencia entre clases useramos la palabra reservada `extends`:
```php
class unaClase{
	public function __construct($parametro1, $parametro2){
		$this->uno = $parametro1;
		$this->dos = $parametro2;
	}
	public function unMetodo1(){
		echo $this->uno;
	}
};

class otraClase extends unaClase{
	public function unMetodoHeredando(){
		echo $this->uno;
	}
};
```

Podemos hacer uso de los `getters`: 
```php
public function getName(){
	return $this->uno;
}
```

También podemos indicar que tipo de valores nos van a retornar las funciones:
```php
public function getName():string{
	return $this->uno;
}
```

Cuando tenemos variables estáticas, para usarlas dentro de los métodos, usaremos `self::` para hacer referencia a la misma clase:
```php
class claseDos{
	static $lavariable = "algo";
	public function usandoSelf(){
		echo self::$lavariable;
	}
}
```

Para modificar una variable privada haremos uso de los `setters`:
```php
class claseDos{
	private $variable = "algo";
	function __construct(){
		$this->variable = $variable 
	}
	public function setValor(string $parametro){
		$this->variable = $parametro
	}
}

```

