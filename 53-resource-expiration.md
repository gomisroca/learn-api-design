# Resource Expiration

- APIs wishing to convey expiration **must** use a timestamp file called expire_time.
- APIs with a relative expiration time **must** define a oneof called expiration.
- APIs **must** return the expiration time in expire_time.
