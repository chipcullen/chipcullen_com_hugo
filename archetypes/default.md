---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
slug: "{{ .Name }}"
description: "{{.Description}}"
---
