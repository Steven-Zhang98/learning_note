```python
class Person:
    def __init__(self):
        self.names = []  # Instance variable to store names

    def set_name(self, user_name):
        self.names.append(user_name)
        return len(self.names) - 1

    def get_name(self, user_id):
        if user_id >= len(self.names):
            return 'There is no such user'
        else:
            return self.names[user_id]

    def delete_name(self, user_id):
        if user_id >= len(self.names) or user_id < 0:
            return 'User does not exist'
        else:
            self.names.pop(user_id)
            return 'User deleted'

```


## unitest
```python
import unittest

class TestPerson(unittest.TestCase):
    def setUp(self):
        self.person = Person()

    def test_add_and_retrieve_user(self):
        user_id = self.person.set_name('Abbas')
        self.assertEqual(self.person.get_name(user_id), 'Abbas')

    def test_delete_user(self):
        user_id = self.person.set_name('Abbas')
        self.person.delete_name(user_id)
        self.assertEqual(self.person.get_name(user_id), 'There is no such user')

    def test_delete_non_existent_user(self):
        user_id = self.person.set_name('Abbas')
        self.assertEqual(self.person.delete_name(user_id + 1), 'User does not exist')

if __name__ == '__main__':
    unittest.main()


```

## TDD
```python
import unittest

class TestPerson(unittest.TestCase):
    def setUp(self):
        self.person = Person()

    def test_add_and_retrieve_user(self):
        user_id = self.person.set_name('Abbas')
        self.assertEqual(self.person.get_name(user_id), 'Abbas')

    def test_delete_user(self):
        user_id = self.person.set_name('Abbas')
        self.person.delete_name(user_id)
        self.assertEqual(self.person.get_name(user_id), 'There is no such user')

    def test_delete_non_existent_user(self):
        self.person.set_name('Abbas')
        self.assertEqual(self.person.delete_name(1), 'User does not exist')

if __name__ == '__main__':
    unittest.main()

```

## integration test

```python
def integration_test():
    person1 = Person()
    person2 = Person()

    # Adding users to the first instance
    id1 = person1.set_name('Abbas')
    id2 = person1.set_name('John')

    # Adding users to the second instance
    id3 = person2.set_name('Mary')

    # Checking for independence between instances
    assert person1.get_name(id1) == 'Abbas'
    assert person1.get_name(id2) == 'John'
    assert person2.get_name(id3) == 'Mary'
    assert person2.get_name(id1) == 'There is no such user'  #  id1 does not exist in person2

    print("Integration test passed")

if __name__ == "__main__":
    integration_test()

```

## white and black

```python
import unittest

class TestPersonWhiteBox(unittest.TestCase):
    def setUp(self):
        self.person = Person()

    def test_list_initially_empty(self):
        self.assertEqual(len(self.person.names), 0)

    def test_list_length_after_addition(self):
        self.person.set_name('Dave')
        self.assertEqual(len(self.person.names), 1)

    def test_list_content_after_addition(self):
        self.person.set_name('Eve')
        self.assertIn('Eve', self.person.names)

    def test_list_content_after_deletion(self):
        user_id = self.person.set_name('Frank')
        self.person.delete_name(user_id)
        self.assertNotIn('Frank', self.person.names)

if __name__ == '__main__':
    unittest.main()

```
