### codet5 small oracle ranking

#### install

```bash
pip install javalang

# original dataset
git clone https://gitlab.com/cawatson/atlas---deep-learning-assert-statements.git
```

处理atlas* dataset, 可以参考[toga datagen.py](https://github.com/microsoft/toga/blob/main/data/atlas_star_datagen.py)



#### atlas* dataset example

```java
org . junit . Assert . assertEquals ( 0 , users . size ( ) )
```


```java
getUsersWaitingNotificationNoWatchExpectEmptyList ( ) { net . jforum . repository . TopicWatchRepository dao = this . newDao ( ) ; net . jforum . entities . Topic topic = new net . jforum . entities . Topic ( ) ; topic . setId ( 13 ) ; java . util . List < net . jforum . entities . User > users = dao . getUsersWaitingNotification ( topic ) ; "<AssertPlaceHolder>" ; } getUsersWaitingNotification ( net . jforum . entities . Topic ) { java . util . List < net . jforum . entities . User > users = session . createQuery ( ( "select<sp>u<sp>from<sp>TopicWatch<sp>tw<sp>" + ( "<sp>inner<sp>join<sp>tw.user<sp>u<sp>where<sp>tw.topic<sp>=<sp>:topic<sp>" + "<sp>and<sp>(tw.read<sp>=<sp>true<sp>or<sp>u.notifyAlways<sp>=<sp>true)" ) ) ) . setEntity ( "topic" , topic ) . setComment ( "topicWatchDAO.getUsersWaitingNotification" ) . list ( ) ; if ( ( users . size ( ) ) > 0 ) { this . markAllAsUnread ( topic ) ; } return users ; }
```

formatted:
```java
getUsersWaitingNotificationNoWatchExpectEmptyList ( ) { 
    net . jforum . repository . TopicWatchRepository dao = this . newDao ( ) ;
    net . jforum . entities . Topic topic = new net . jforum . entities . Topic ( ) ;
    topic . setId ( 13 ) ;
    java . util . List < net . jforum . entities . User > users = dao . getUsersWaitingNotification ( topic ) ;
    "<AssertPlaceHolder>" ;
} 
getUsersWaitingNotification ( net . jforum . entities . Topic ) { 
    java . util . List < net . jforum . entities . User > users = session . createQuery ( ( "select<sp>u<sp>from<sp>TopicWatch<sp>tw<sp>" + ( "<sp>inner<sp>join<sp>tw.user<sp>u<sp>where<sp>tw.topic<sp>=<sp>:topic<sp>" + "<sp>and<sp>(tw.read<sp>=<sp>true<sp>or<sp>u.notifyAlways<sp>=<sp>true)" ) ) ) . setEntity ( "topic" , topic ) . setComment ( "topicWatchDAO.getUsersWaitingNotification" ) . list ( ) ;
    if ( ( users . size ( ) ) > 0 ) { 
        this . markAllAsUnread ( topic ) ;
    } 
    return users ;
}
```