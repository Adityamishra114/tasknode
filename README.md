# Real Estate

This repository contains Real Estate app built  using Mern stack.Please follow the instructions to set it up.

***Features***
1. Admin Section
2. Product categories
3. interactive chat 
4. Search Options

> [Real Estate](https://mern-estate-4kb3.onrender.com/)

### Instructions
1. Clone the repo and run ``npm install``
2. From the app folder run ``npm run dev``
---
**Creating Sign up**
```js
export const signup = async (req, res, next) => {
  const { username, email, password } = req.body;
  const hashedPassword = bcryptjs.hashSync(password, 10);
  const newUser = new User({ username, email, password: hashedPassword });
  try {
    await newUser.save();
    res.status(201).json('User created successfully!');
  } catch (error) {
    next(error);
  }
};

```
**Sign In Form**
```html
  <form className="flex flex-col gap-4">
        <input
          type="email"
          placeholder="email"
          id="email"
          className="border p-3 rounded-lg"
        />
        <input
          type="password"
          placeholder="password"
          id="password"
          className="border p-3 rounded-lg"
        />
        <button
          className="bg-slate-700 text-white p-3 rounded-lg uppercase hover:opacity-95 disable:opacity-80"
        >
          {loading ? "Loading..." : "Sign In"}
        </button>
      </form>
```
