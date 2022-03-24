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
<img src="https://i.ibb.co/8KyzpVT/1.png" alt="Nullsafe Operator img" width="800">

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
<img src="https://i.ibb.co/3fb7H7J/2.png" alt="Nullsafe Operator img" width="800">


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
<img src="https://i.ibb.co/kGT9zSV/3.png" alt="Null Coalescing Operator img" width="800">

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

$type = match

echo $type;
```
<img src="https://i.ibb.co/ypMZBVs/4.png" alt="Match Expression img" width="800">