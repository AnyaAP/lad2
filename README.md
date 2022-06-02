# lab2

Part |

1) Создание репозитория
```
    git init
```

2)
```
    git commit
    git remote add origin 
# Команда git remote add используется для создания записи о новом подключении к удаленному репозиторию.
    git push

    git clone

    # есть у нас локальная ветка
    git checkout -b mybranch

    # Создаем ветку на remote
    git push -u origin mybranch

    # Можно выбрать другое имя для создаваемой ветки на remote.
    git push -u origin main
```

3) Создаём файл main.cpp
```
    cat > "main.cpp" << EOF
      #include <iostream>

      using namespace std;
      int main(){
        cout << "Hello world" << endl;
      }
      EOF
```

4) Добавляем созданный файл в репозиторий
```
      git add "main.cpp"
```
5) Коммитим файл с осознанным комментарием
```
    git commit -m "MyFirstCommit"
```

6) 
```
    edit "main.cpp"
    #include <iostream>
    #include <string>

    using namespace std;
    int main(){
     string name;
     cin >> name;
     cout << "Hello world from " << name << endl;
    }
```
7) 
```
    git commit -m "newCommit"
```
Повторно писать команду git add не надо, т.к. файл уже был добавлен.

8) 
```    
    git push
```
----------------------------------------------------------------------------------------------------------------------

Part ||
1) 
```
    git checkout -b patch1
```
2) 
```    
    edit "main.cpp"
   #include <iostream>
   #include <string>

   int main(){
    std::string name;
    std::cin >> name;
    std::cout << "Hello world from " << name << std::endl;
   }
```

3) 
```   
    git commit -m "Fixed cpp file"
    git push -u origin patch1
```
4) 
```
    pull-request patch1 -> master
```
5) 
```    
    edit "main.cpp"
   #include <iostream>
   #include <string>

   int main(){
    string name; \\ name
    std::cin >> name; \\ input
    std::cout << "Hello world from " << name << std::endl;
   }
```
7) 
```   
    git commit -m "Added comments"
    git push -u origin patch1
```
8) 
```    
    git pull origin
```
9) 
```    
    git log
```
10) 
```    
    git branch -d patch1 // delete
```
-----------------------------------------------------------------------------------------------------------
Part|||
1) 
```    
    git checkout -b patch2
```
2) 
```    
    clang-format -i -style=Mozilla "main.cpp"
```
3) 
```    
    git commit -a -m "Changed code style in cpp file"
    git push -u origin patch2
```
4) 
```    
    edit "main.cpp"
    int main(){
       string name; \\ .....
       std::cin >> name; \\ Ввод данных
       std::cout << "Hello world from " << name << std::endl;
    }
```
6) 
```    
    git pull origin main
    git rebase main
    edit "Hello world.cpp"
    git commit -a -m "Update Hello world.cpp"
    git rebase --continue
```
7) 
```    
    git push -f origin patch2
```
8) 
```    
    pull-request patch2 -> master
    git merge patch2 master
```
