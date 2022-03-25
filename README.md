# PHP 8 Course

* The Nullsafe Operator => ?->

```
class User {
    public function profile()
    {
        return new Profile;
    }
}

class Profile {
    public function employment()
    {
        return "Kalin";
    }
}

$user = new User();
echo $user->profile()?->employment();
```
<img src="https://i.ibb.co/SmP4mmw/Nullsafe-Operator-1.png" alt="Nullsafe-Operator-1" width="800">

```
class User {
    public function profile()
    {
        return null;
    }
}

class Profile {
    public function employment()
    {
        return "Kalin";
    }
}

$user = new User();
var_dump($user->profile()?->employment());
```
<img src="https://i.ibb.co/pzxsFQM/Nullsafe-Operator-2.png" alt="Nullsafe-Operator-2" wdith="800">


* Null Coalescing Operator => ??
```
class User {
    public function profile()
    {
        return null;
    }
}

class Profile {
    public function employment()
    {
        return "Kalin";
    }
}

$user = new User();
echo $user->profile()?->employment() ?? 'Not provided';
```
<img src="https://i.ibb.co/QJghv6P/Null-Coalescing-Operator.png" alt="Null-Coalescing-Operator" width="800">

* Match Expression => match(get_class())

```
class Conversation{}

$obj = new Conversation();

//switch(get_class($obj))
//{
//  case 'Conversation':
//    $type = 'started conversation';
//    break;
    
//  case 'Reply':
//    $type = 'started reply conversation';
//    break;
    
//  case 'Comment':
//    $type = 'started comment conversation';
//    break;
//}

$type = match(get_class($obj))
{
	'Conversation' => 'started conversation',
  	'Reply' => 'started reply conversation',
  	'Comment' => 'started comment conversation',
};

var_dump($type);
```
<img src="https://i.ibb.co/fDZn4BL/Match-Expression.png" alt="Match-Expression" width="800">

* Constructor Property Promotion => __constructor(protected $name)

```
//class User {
//	protected $name;
//  	public function __construct($name)
//    {
//      $this->name = $name;
//    }
//}

//class Plan {
//	protected $name;
//  	public function __construct($name)
//    {
//    	$this->name = $name;
//    }
//}

//class Signup {
//	protected User $user;
//  	protected Plan $plan;
//  	public function __construct($user, $plan)
//    {
//    	$this->user = $user;
//      	$this->plan = $plan;
//    }
//}

//$user = new User("Kalin");
//$plan = new Plan("PHP8");

//$signup = new Signup($user, $plan);

//var_dump($signup);


class User {
  	public function __construct(protected $name)
    {
    }
}

class Plan {
  	public function __construct(protected string $name = 'PHP')
    {
    }
}

class Signup {
  	public function __construct(protected User $user, protected Plan $plan)
    {
    }
}

$user = new User("Kalin");
$plan = new Plan();

$signup = new Signup($user, $plan);

var_dump($signup);
```
<img src="https://i.ibb.co/xSHFX9v/Constructor-Property-Promotion.png" alt="Constructor-Property-Promotion" width="800">

* $obj::class
```
class Conversation {
    //
}

$obj = new Conversation();

$type = match($obj::class)
{
    'Conversation' => 'started conversation',
    'Reply' => 'started reply',
    'Comment' => 'started comment',
};

var_dump($type);
```
<img src="https://i.ibb.co/XjvPFsK/obj-class.png" alt="obj-class" width="800">

* Named Parameters

```
class Invoice {
    private $description;
    private $total;
    private $date;
    private $paid;

    public function __construct($description, $total, $date, $paid)
    {
        $this->description = $description;
        $this->total = $total;
        $this->date = $date;
        $this->paid = $paid;
    }
}

$invoice = new Invoice(
    description: 'Customer Installation',
    total: 1000,
    date: new DateTime(),
    paid: true
);

var_dump($invoice);
```
<img src="https://i.ibb.co/c1FhDrg/Named-Parameters.png" alt="Named-Parameters" width="800">