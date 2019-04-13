---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120785"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
구성 된 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다. 이 요소를 사용할 수만 있습니다 경우는 `mode` 특성을 `<cookieHandler>` 요소는 "Default" 또는 "청크"입니다.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<chunkedCookieHandler>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|chunkSize|HTTP 쿠키에 대 한 HTTP 쿠키 데이터의 문자, 최대 크기입니다. 청크 크기를 조정할 때 주의 해야 합니다. 웹 브라우저 쿠키 및 도메인 별로 허용 되는 수의 크기에 서로 다른 제한이 있습니다. 예를 들어 원래 Netscape 사양에는 이러한 제한을 규정 된: 4096 바이트로 쿠키 헤더 (메타 데이터를 쿠키 값 뿐 아니라 포함) 및 도메인 별로 20 쿠키 300 쿠키 총입니다. 기본값은 2000입니다. 필수 요소.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성 된 <xref:System.IdentityModel.Services.CookieHandler> 는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 및 쓰기 쿠키를 사용 하 여 합니다.|  
  
## <a name="remarks"></a>설명  
 지정 하는 경우는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 설정 하 여는 `mode` 특성을 `<cookieHandler>` "Default" 또는 "Chunked" 요소를 포함 하 여 쿠키를 읽고 사용 하는 쿠키 처리기는 청크 크기를 지정할 수 있습니다는 `<chunkedCookieHandler>` 자식 요소 및 설정을 해당 `chunkSize` 특성입니다. 경우는 `<chunkedCookieHandler>` 요소가 없으면, 2000 바이트의 기본 청크 크기가 사용 됩니다. 이 요소가 있을 수 없습니다 될 때 지정 되는 `mode` 특성은 "Custom"로 설정 합니다.  
  
 합니다 `<chunkedCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 3000 바이트 청크에서 쿠키를 작성 하는 청크 분할된 쿠키 처리기를 구성 합니다.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
