```uml
@startuml

ユーザー -> Webシステム: 検索
Webシステム -> DBシステム: 検索処理
DBシステム -> DBシステム: 検索処理
DBシステム --> Webシステム: 検索結果
Webシステム --> ユーザー: 検索結果

@enduml
```
