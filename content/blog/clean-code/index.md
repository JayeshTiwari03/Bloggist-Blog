---
title: Clean Code
date: "2022-08-2T15:12:03.284Z"
description: "Cleaner Code Techniques"
---

# Cleaner Code Techniques

### Proper Spacing and Returns

![Line Between Statements](https://eslint.org/docs/rules/padding-line-between-statements)

### Clean Functions

// Descriptive Names

```
function addAdminUser(user) {
    const userData = {...user, type: 'Admin'};

    // adds user to DB
}
```

// Standardization of Naming

```
function getAdminById(id) {
    //  gets admin
}

function getUserById(id) {
    // gets user
}
```

### Clean Func

```
function getNonPrimaryUsers(user) {
    if(getIsUserPrimaryActiveAccount(user)) {
        return user.subMembers;
    } else {
        return new Error('User is not Primary Account Holder.');
    }
}

function getIsUserPrimaryActiveAccount(user) {
    const isPrimaryAccount = user.isPrimaryAccount === true;
    const isActive = user.isActive === true;

    return isActive && isPrimaryAccount;
}
```

### Another Example

```
// Clean Code: Encapsulating Conditionals Challenge

function getLoadingState(state) {
    if(hasUserLoadedSuccesfully(state)) {
        return 'Finished Loading';
    }

    if(isUserLoadingSuccesfully(state)) {
        return 'Loading...';
    }

    return 'Error occured';
}

function hasUserLoadedSuccesfully(state) {
    return !!state.user && state.loading === false && state.hasError === false;
}

function isUserLoadingSuccesfully(state) {
    return state.user === null && state.loading  === true && state.hasError === false;
}
```

New day, new techniques

_Cheers_
