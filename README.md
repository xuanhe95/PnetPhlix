# PnetPhlix

## PnetPhlix是一个电影推荐系统。

### 项目说明
---

---

### 👨 User
User类用来记录用户的相关数据：
- get_full_name() 获取用户姓名。
- get_email() 获取用户email地址。
- get_watch_history() 获取用户的观看历史。

### 📦 UserDatabase
UserDatabase用来处理并储存用户数据库。
- load(const string& filename) 方法解析文件，并将用户以TreeMap的形式储存。
- get_user_from_email(const string& email) const 方法通过用户名称获取其email地址。

### 🎬 Movie
Movie类用来记录电影的相关数据：
- get_id() 获取电影ID。
- get_title() 获取电影标题。
- get_release_year() 获取出品年份。
- get_rating() 获取评价。
- get_directors() 获取导演列表。
- get_actors() 获取演员列表。
- get_genres() 获取电影类型。

### 📦 MovieDatabase
MovieDatabase用来处理并储存电影数据库。
- load(const string& filename)

-
- 过滤用户已经观看过的电影。

### 👏 Recommender
Recommender类用来计算并向用户推荐电影。
- recommend_movies(const string& user_email, int movie_count) 方法用来处理并计算电影的推荐度：
- 使用TreeMultiMap记录用户email地址与MovieAndRank的关系。

- 从用户的电影观看记录中获得电影的导演，演员和类型。
  - 其他电影中如果有相同导演，则推荐度增加20。
  - 其他电影中如果有相同演员，则推荐度增加30。
  - 其他电影中如果是相同题材，则推荐度增加1。 
- 过滤掉用户已经观看过的电影。
- 按推荐度高低排序后，根据movie_count返回对应长度的推荐列表。

#### 🌟 MovieAndRank
MovideAndRank方法体用来记录电影的推荐度评分。

### 🌿 TreeMultimap<typename KeyType, typename ValueType>
TreeMultimap通过模版实现了TreeMap的功能。

- insert(const KeyType& key, const ValueType& value) 方法插入键值对。
- find(const KeyType& key) 方法返回迭代器。
- 根据比较关系新建Node并插入在合理的位置。

#### 🧶 Node
- Node方法体作为树状数据结构的节点
