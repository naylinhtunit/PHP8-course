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
<img src="https://i.ibb.co/8KyzpVT/1.png" alt="Nullsafe Operator img" border="0">