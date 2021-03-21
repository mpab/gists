# IIS Internet Information Server

## Context

HTTP PUT DELETE WebDAV 405

## Problem

IIS returns 405 Method Not Allowed error with PUT or DELETE Request

## Solution

Disable WebAV using web.config file in site root

[Before link](files/webdav-issue-web.config)

[After link](files/webdav-fix-web.config)
