---
title: bypasslist의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: a04cca3e57af5cc422776c5b2444a140e86f98b9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354260"
---
# <a name="remove-element-for-bypasslist-network-settings"></a>\<제거 > bypasslist (네트워크 설정)에 대 한 요소

프록시 무시 목록에서 IP 주소 또는 DNS 이름을 제거합니다.

\<configuration>\
\<system.net>\
\<defaultProxy>\
\<bypasslist>\
\<remove>

## <a name="syntax"></a>구문

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|**특성**|**설명**|
|-------------------|---------------------|
|`address`|IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|**요소**|**설명**|
|-----------------|---------------------|
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.|

## <a name="remarks"></a>설명

`remove` 요소 IP 주소 또는 프록시 서버를 바이패스 하는 주소 목록에서 DNS 서버 이름을 설명 하는 정규식을 제거 합니다. 구성 계층 구조의 상위 수준 또는 구성 파일에서 주소를 이전 정의 되었습니다.

에 대 한 값을 `address` 특성에는 IP 주소 또는 호스트 이름 집합을 설명 하는 정규식을 사용 해야 합니다.

정규식에 대 한 자세한 내용은 다음을 참조 하세요. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.

## <a name="configuration-files"></a>구성 파일

이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.

## <a name="example"></a>예제

Adventure-works.com 도메인에 대 한 이전 정의 제거 하 고 바이패스 목록에 contoso.com 도메인을 추가 하는 다음 예제입니다.

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a>참고자료

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
