# Anonymous User Role 

## CAUSE:
The 'anonymous' role was mistakenly set as the default in the database, which is not an accepted role.

## FIX:
The default role 'anonymous' is not valid in the database. The issue was resolved by updating the default role to 'user' in user_model.py

>>> role: Mapped[UserRole] = Column(SQLAlchemyEnum(UserRole), default=UserRole.USER, nullable=False)
