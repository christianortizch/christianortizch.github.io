+++ 
draft = true
title = ""
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++
{{ define "title" }}
  {{ .Title }} · {{ .Site.Title }}
{{ end }}
{{ define "content" }}
  <section class="container post">
    <article>
      <header>
        <div class="post-title">
          <h1 class="title">{{ .Title }}</h1>
        </div>
        <div class="post-meta">
          <div class="date">
            <span class="posted-on">
              <i class="fas fa-calendar"></i>
              <time datetime='{{ .Date.Format "2006-01-02" }}'>
                {{ .Date.Format (.Site.Params.dateFormat | default "January 2, 2006" ) }}
              </time>
            </span>
            <span class="reading-time">
              <i class="fas fa-clock"></i>
              {{ i18n "reading_time" .ReadingTime }}
            </span>
          </div>
          {{ with .Page.Params.Categories }}{{ partial "taxonomy/categories.html" . }}{{ end }}
          {{ with .Page.Params.Tags }}{{ partial "taxonomy/tags.html" . }}{{ end }}
        </div>
      </header>
