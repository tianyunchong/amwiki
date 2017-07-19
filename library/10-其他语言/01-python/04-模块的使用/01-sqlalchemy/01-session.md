### 初始化session
```python
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

BaseModel = declarative_base()
dbconnectStr = 'mysql+mysqldb://%s:%s@%s/%s?charset=utf8' % ("root", "123456","localhost", "test")
engine = create_engine(dbconnectStr, echo=False)
DB_Session = sessionmaker(bind=engine)
session = DB_Session()                                                             
```
