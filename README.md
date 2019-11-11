# IE11 issues faced by me

## Psuedo elements - CSS not applied when display flex is used in microsoft edge
https://stackoverflow.com/questions/56712661/css-not-applied-when-display-flex-is-used-in-microsoft-edge
//problem
```
const text = styled(div)`
    display: flex;
    align-items: center;
    color: gray;
    margin-bottom: 24px;
    ::before, ::after {    //doesn't work
        content: '';
        width: 100%;
        border-top: 1px solid gray;
      }
    ::before {
        margin-right: 8px;
      }
    ::after {
        margin-left:8px;
  }
`;
<text>OR</text>
```
//solution
```
const text = styled(div)`
    display: flex;
    align-items: center;
    color: gray;
    margin-bottom: 24px;
    ::before, ::after {
        content: '';
        display:block;
        flex-grow:1;
        border-top: 1px solid gray;
      }
    ::before {
        margin-right: 8px;
      }
    ::after {
        margin-left:8px;
  }
`;
<text>OR</text> 
```

## using getBoundingClientRect
fix: https://github.com/ticketmaster/aurora/pull/573/files
description: using x and y coordinates doesn't work in IE11 and MSEdge. We have to make use of top and left instead

## multiple box shadows doesn't work in IE11 virtual image
https://stackoverflow.com/questions/57368041/multiple-box-shadows-doesnt-work-in-msedge
