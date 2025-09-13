---
active_lock_reason: 
assignee: 
assignees: []
author_association: OWNER
closed_at: 
comments: 0
comments_url: https://api.github.com/repos/gghatano/gialog/issues/28/comments
created_at: '2022-11-15T02:16:31Z'
events_url: https://api.github.com/repos/gghatano/gialog/issues/28/events
html_url: https://github.com/gghatano/gialog/issues/28
id: 1449049041
labels: []
labels_url: https://api.github.com/repos/gghatano/gialog/issues/28/labels{/name}
locked: false
milestone: 
node_id: I_kwDOH0C-AM5WXrvR
number: 28
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
  url: https://api.github.com/repos/gghatano/gialog/issues/28/reactions
repository_url: https://api.github.com/repos/gghatano/gialog
state: open
state_reason: 
timeline_url: https://api.github.com/repos/gghatano/gialog/issues/28/timeline
title: mermaidは表示されない
updated_at: '2022-11-15T02:16:31Z'
url: https://api.github.com/repos/gghatano/gialog/issues/28
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
```mermaid
    gitGraph
      commit id: "create"
      branch release
      branch develop
      branch feature1
      branch feature2
      checkout main
      commit id: "start"
      checkout develop
      merge main
      checkout feature1
      merge develop
      commit id: "update1"
      commit id: "update2"
      checkout develop
      merge feature1
      checkout feature2
      merge develop
      commit id: "team-review1"
      commit id: "team-review2"
      checkout develop
      merge feature2
      checkout release
      merge develop
      commit id: "GL-review1"
      checkout main
      merge release
      checkout develop
      merge release
```
