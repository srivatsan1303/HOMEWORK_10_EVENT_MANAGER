# Error during user creation

## cause:
No validation was performed when attempting to create a user with an email ID that already exists.

## Fix:
Implemented email ID validation and set appropriate error message for duplicate entries.
>>> existing_email = await UserService.get_by_email(db, user.email)
    if existing_email:
        raise HTTPException(status_code=status.HTTP_400_BAD_REQUEST, detail="Email ID already exists")
