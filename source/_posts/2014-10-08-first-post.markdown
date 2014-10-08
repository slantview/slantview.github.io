---
layout: post
title: "First Post"
date: 2014-10-08 15:51:32 -0700
comments: true
categories: test tech
---

Hello and welcome to my new Octopress blog.

Test Code block:

```Go
func (c *Client) NewDropletRequest(name string) *DropletRequest {
    dr := &DropletRequest{
        Name:              name,
        Region:            DefaultRegionSlug,
        Size:              DefaultSizeSlug,
        Image:             DefaultImageSlug,
        Backups:           false,
        IPv6:              false,
        PrivateNetworking: false,
        UserData:          "",
    }

    return dr
}

func (c *Client) CreateDroplet(request *DropletRequest) (*Droplet, error) {
    var dropletResponse DropletResponse

    apiErr := c.Post("droplets", request, &dropletResponse, nil)
    if apiErr != nil {
        return nil, errors.New(fmt.Sprintf("API Error: %s", apiErr.Message))
    }

    return dropletResponse.Droplet, nil
}
```