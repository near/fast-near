## Build and run via yarn:

```
yarn
FAST_NEAR_REDIS_URL=<redis_ip> FAST_NEAR_NODE_URL=<rpc_endpoint> yarn start
```

## Build and run with docker:

```
docker build -t fastrpc .
docker run -d -e FAST_NEAR_REDIS_URL=<redis_ip> -e FAST_NEAR_NODE_URL=<rpc_endpoint> fastrpc 
```

## Call view method

### POST

You can post either JSON or binary body, it's passed raw as input to given method.


URL format:

```
https://fastrpc.mainnet.near.org/account/<contract_account_id>/view/<method_name>
```

#### Examples

```
http post https://fastrpc.mainnet.near.org/account/vlad.tkn.near/view/ft_balance_of account_id=vlad.near
```

### GET

Parameters are passed as part of URL query.

URL format:

```
https://fastrpc.mainnet.near.org/account/<contract_account_id>/view/<method_name>?<arg_name>=<string_arg_value>&<arg_name.json>=<json_arg_value>
```

#### Examples

##### String parameters:

```
curl 'https://fastrpc.mainnet.near.org/account/vlad.tkn.near/view/ft_balance_of?account_id=vlad.near'
```

[https://fastrpc.mainnet.near.org/account/vlad.tkn.near/view/ft_balance_of?account_id=vlad.near](https://fastrpc.mainnet.near.org/account/vlad.tkn.near/view/ft_balance_of?account_id=vlad.near)


##### JSON parameters:

```
curl --globoff 'https://fastrpc.mainnet.near.org/account/lands.near/view/web4_get?request.json={"path":"/"}'
```

[https://fastrpc.mainnet.near.org/account/lands.near/view/web4_get?request.json={"path":"/"}](https://fastrpc.mainnet.near.org/account/lands.near/view/web4_get?request.json={"path":"/"})


##### Number parameters (passed as JSON):


```
curl 'https://fastrpc.mainnet.near.org/account/lands.near/view/getChunk?x.json=0&y.json=0'
```

[https://fastrpc.mainnet.near.org/account/lands.near/view/getChunk?x.json=0&y.json=0](https://fastrpc.mainnet.near.org/account/lands.near/view/getChunk?x.json=0&y.json=0)




