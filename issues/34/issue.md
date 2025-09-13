---
active_lock_reason: 
assignee: 
assignees: []
author_association: OWNER
closed_at: 
comments: 0
comments_url: https://api.github.com/repos/gghatano/gialog/issues/34/comments
created_at: '2023-06-05T09:41:03Z'
events_url: https://api.github.com/repos/gghatano/gialog/issues/34/events
html_url: https://github.com/gghatano/gialog/issues/34
id: 1741392516
labels: []
labels_url: https://api.github.com/repos/gghatano/gialog/issues/34/labels{/name}
locked: false
milestone: 
node_id: I_kwDOH0C-AM5ny4qE
number: 34
performed_via_github_app: 
reactions:
  "+1": 0
  "-1": 0
  confused: 0
  eyes: 0
  heart: 0
  hooray: 0
  laugh: 0
  rocket: 0
  total_count: 0
  url: https://api.github.com/repos/gghatano/gialog/issues/34/reactions
repository_url: https://api.github.com/repos/gghatano/gialog
state: open
state_reason: 
timeline_url: https://api.github.com/repos/gghatano/gialog/issues/34/timeline
title: 'ABC098-D XOR sum 2 '
updated_at: '2023-06-05T09:41:03Z'
url: https://api.github.com/repos/gghatano/gialog/issues/34
user:
  avatar_url: https://avatars.githubusercontent.com/u/5264958?v=4
  events_url: https://api.github.com/users/gghatano/events{/privacy}
  followers_url: https://api.github.com/users/gghatano/followers
  following_url: https://api.github.com/users/gghatano/following{/other_user}
  gists_url: https://api.github.com/users/gghatano/gists{/gist_id}
  gravatar_id: ''
  html_url: https://github.com/gghatano
  id: 5264958
  login: gghatano
  node_id: MDQ6VXNlcjUyNjQ5NTg=
  organizations_url: https://api.github.com/users/gghatano/orgs
  received_events_url: https://api.github.com/users/gghatano/received_events
  repos_url: https://api.github.com/users/gghatano/repos
  site_admin: false
  starred_url: https://api.github.com/users/gghatano/starred{/owner}{/repo}
  subscriptions_url: https://api.github.com/users/gghatano/subscriptions
  type: User
  url: https://api.github.com/users/gghatano

---
## 概要
- 問題は[これ](https://atcoder.jp/contests/abc098/tasks/arc098_b)
- 提出結果は[WA](https://atcoder.jp/contests/abc098/submissions/42018477)
- 何が悪いのかわからん

```python
#!/usr/bin/python3
import sys
# import bisect,collections,copy,heapq,itertools,math,numpy,string
sys.setrecursionlimit(10**6)
input = lambda: sys.stdin.readline().rstrip()
from collections import defaultdict, deque


def main():
    N = int(input())
    A = list(map(int, input().split()))
    dq = deque()
    
    now = 0
    ans = 0

    for a in A:
        ans += 1

        if len(dq) > 0 and now ^ a == now + a:
            ans += len(dq)
        
        while len(dq) > 0 and now ^ a != now + a:
            pop = dq.pop()
            now ^= pop
        
        now += a 
        dq.appendleft(a)
    
    print(ans)
            
    return(0)

if __name__ == '__main__':
 main()

```

## 考えたこと
- しゃくとり法
  - A xor B == A + B は、bit表示したときに、桁あふれがない、ということ
  - A,B,C で桁あふれがなければ、A,B、B,Cでもあふれない
  - しゃくとり法で、nowにaを追加するとき、now xor a == now + a なら、len(dq)だけ答えに追加する
  - 条件を満たさなかったら、満たすまで、nowから削る
    - xorの逆演算は、xor。削るときには、xorで足せばいい  