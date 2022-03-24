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
echo $user->profile()?->employment();
```
<img src="https://i.ibb.co/3fb7H7J/2.png" alt="Nullsafe Operator img" width="800">