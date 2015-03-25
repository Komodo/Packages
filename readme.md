# Resource Guidelines

A Komodo Resource will work best if

 * It's hosted in it's own GitHub repository
 * It has a readme in the root of it's repository
 * It utilizes GitHub releases to distribute downloadable copies of the resource

Although all of the above is optional, we highly encourage you to follow these
guidelines.

## Adding a Resource

There are 3 ways to add a resource, fully-automatic, semi-automatic and manual.
Both the automatic ways require you to use GitHub as described above.

Whatever method you use, you will need to start by forking this repository.
Edit the category file that your Resource relates to and once you are done
making the changes via the method you choose you will need to make a pull
request to get your changes applied.

Note that changes will not instantly take effect, the Komodo Resources section
is updated only once every hour.

### Automatic

With Automatic resources all you do is supply the name and GitHub url of your
resource, we will take care of the rest. To do this, use the following format:

```yaml
Resource Name: https://github.com/MyUsername/MyRepository
```

### Semi-Automatic

Say you want us to retrieve all your repository data for you, but you want to
override certain information that is being supplied by GitHub. You can do this
by using the following format:

```yaml
Resource Name:
    html_url: https://github.com/MyUsername/MyRepository # Required
    owner: 
        login: MyOtherNickname # Example
    readme: 
        content: >
                  Foo
```

To find out what fields you can override please check out the
[Github API documentation](https://developer.github.com/v3/repos/#get)

### Manual

Say you're not using GitHub or your repository structure is not supported by
our parser, you can then manually provide us with all of your Resource information.

You do this by providing us with your Resource information formatted in the same
way as a repository is formatted in the [Github API documentation](https://developer.github.com/v3/repos/#get).

```yaml
Resource Name:
    # Required Fields
    owner:
        login: MyName
        gravatar_id: fbf0600881da69934bad33192694d484 # Optional
        html_url: https://github.com/MyName
    created_at: 2014-03-24T00:00:00Z
    updated_at: 2014-03-24T00:00:00Z

    # The location where your Resource may be downloaded
    raw_url: https://raw.github.com/Foo/Bar/file.txt

    # Optional Fields
    description: My Description
    readme: 
        content: >
                  Foo
    homepage: https://..
```
