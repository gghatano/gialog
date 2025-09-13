---
active_lock_reason: 
assignee: 
assignees: []
author_association: OWNER
closed_at: 
comments: 0
comments_url: https://api.github.com/repos/gghatano/gialog/issues/35/comments
created_at: '2023-06-05T10:21:40Z'
events_url: https://api.github.com/repos/gghatano/gialog/issues/35/events
html_url: https://github.com/gghatano/gialog/issues/35
id: 1741462727
labels: []
labels_url: https://api.github.com/repos/gghatano/gialog/issues/35/labels{/name}
locked: false
milestone: 
node_id: I_kwDOH0C-AM5nzJzH
number: 35
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
  url: https://api.github.com/repos/gghatano/gialog/issues/35/reactions
repository_url: https://api.github.com/repos/gghatano/gialog
state: open
state_reason: 
timeline_url: https://api.github.com/repos/gghatano/gialog/issues/35/timeline
title: 'ABC289-C '
updated_at: '2023-06-05T10:21:40Z'
url: https://api.github.com/repos/gghatano/gialog/issues/35
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
- https://atcoder.jp/contests/abc289/tasks/abc289_c
- pythonで書いた

```python
#!/usr/bin/python3
import sys
# import bisect,collections,copy,heapq,itertools,math,numpy,string
sys.setrecursionlimit(10**6)
input = lambda: sys.stdin.readline().rstrip()
from collections import defaultdict


def main():
    N,M = map(int, input().split())  

    A = []
    for _ in range(M):
        tmp = 1
        n = int(input())
        L = list(map(int, input().split()))
        for l in L:
            tmp += 2**l
        A.append(tmp)

    ans = 0 
    for bit in range(2**M):
        a = 0
        for i in range(M):
            if (bit >> i) & 1:
                a = a | A[i]
        
        if a == 2**(N+1)-1:
            ans += 1


    print(ans)
    return(0)

if __name__ == '__main__':
 main()

```

## 感想・その他
- bitで管理して足し算するのが自然に思えた
