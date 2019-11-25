---
title: <httpListener> 요소(네트워크 설정)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088384"
---
# <a name="httplistener-element-network-settings"></a>\<httpListener > 요소 (네트워크 설정)
<xref:System.Net.HttpListener> 클래스에서 사용 하는 매개 변수를 사용자 지정 합니다.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<설정**](settings-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpListener >**

## <a name="syntax"></a>구문  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Type  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|unescapeRequestUrl|<xref:System.Net.HttpListener> 인스턴스가 변환 된 URI 대신 이스케이프 되지 않은 원시 URI를 사용 하는지 여부를 나타내는 부울 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[설정](settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>주의  
 **UnescapeRequestUrl** 특성 은% 인코딩된 값이 변환 되 고 다른 정규화 단계를 수행 하는 변환 된 uri 대신 이스케이프 되지 않은 원시 uri를 사용 <xref:System.Net.HttpListener> 여부를 나타냅니다.  
  
 <xref:System.Net.HttpListener> 인스턴스가 `http.sys` 서비스를 통해 요청을 받으면 `http.sys`에서 제공 하는 URI 문자열의 인스턴스를 만들고 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> 속성으로 노출 합니다.  
  
 `http.sys` 서비스는 두 개의 요청 URI 문자열을 노출 합니다.  
  
- 원시 URI  
  
- 변환 된 URI  
  
 원시 URI는 HTTP 요청의 요청 줄에 제공 된 <xref:System.Uri?displayProperty=nameWithType>입니다.  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 위에서 언급 한 요청에 대해 `http.sys`에서 제공 하는 원시 URI는 "/path/"입니다. 이는 네트워크를 통해 전송 된 HTTP 동사 뒤에 나오는 문자열을 나타냅니다.  
  
 `http.sys` 서비스는 HTTP 요청 줄에 제공 된 URI와 호스트 헤더를 사용 하 여 요청에 제공 된 정보 로부터 변환 된 URI를 만들어 요청을 전달 해야 하는 원본 서버를 확인 합니다. 요청의 정보를 등록 된 URI 접두사 집합과 비교 하 여이 작업을 수행 합니다. HTTP 서버 SDK 설명서는 HTTP_COOKED_URL 구조체로 변환 된이 URI를 참조 합니다.  
  
 요청을 등록 된 URI 접두사와 비교할 수 있으려면 요청에 대 한 일부 정규화를 수행 해야 합니다. 위의 샘플에서 변환 된 URI는 다음과 같습니다.  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` 서비스는 <xref:System.Uri.Host%2A?displayProperty=nameWithType> 속성 값과 요청 줄의 문자열을 결합 하 여 변환 된 URI를 만듭니다. 또한 `http.sys` 및 <xref:System.Uri?displayProperty=nameWithType> 클래스는 다음을 수행 합니다.  
  
- 모든% 인코딩된 값을 이스케이프 해제 합니다.  
  
- 백분율 인코딩된 ASCII가 아닌 문자를 UTF-16 문자 표현으로 변환 합니다. UTF-8 및 ANSI/DBCS 문자는 유니코드 문자 (% uXXXX 형식을 사용 하는 유니코드 인코딩)와도 지원 됩니다.  
  
- 경로 압축과 같은 다른 정규화 단계를 실행 합니다.  
  
 요청은 백분율 인코딩 값에 사용 된 인코딩에 대 한 정보를 포함 하지 않으므로 백분율 인코딩된 값을 구문 분석 하 여 올바른 인코딩을 결정 하지 못할 수 있습니다.  
  
 따라서 `http.sys`는 프로세스를 수정 하기 위한 두 개의 레지스트리 키를 제공 합니다.  
  
|레지스트리 키|기본값|설명|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|0 인 경우 u t f-8로 인코딩된 Url만 허용 `http.sys`.<br /><br /> 0이 아닌 경우, `http.sys`는 요청에서 ANSI 인코딩 또는 DBCS 인코딩된 Url도 허용 합니다.|  
|FavorUTF8|1|0이 아닌 경우 `http.sys` 항상 URL을 u t f-8로 디코드 하려고 시도 합니다. 이 변환이 실패 하 고 EnableNonUTF8가 0이 아닌 경우 Http.sys는 ANSI 또는 DBCS로 디코드 하려고 시도 합니다.<br /><br /> 0 (및 EnableNonUTF8가 0이 아닌 경우)은이를 ANSI 또는 DBCS로 디코드 하려고 시도 `http.sys` 합니다. 성공 하지 못하면 UTF-8 변환을 시도 합니다.|  
  
 <xref:System.Net.HttpListener>에서 요청을 받으면 `http.sys`의 변환 된 URI를 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 사용 합니다.  
  
 Uri에서 문자 및 숫자 이외의 문자를 지원 해야 합니다. 예를 들어 다음 URI는 고객 번호 "1/3812"에 대 한 고객 정보를 검색 하는 데 사용 됩니다.  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Uri (% 2F)의 백분율 인코딩된 슬래시를 적어둡니다. 이 경우 슬래시 문자는 데이터를 나타내지만 경로 구분 기호는 아니기 때문에이 작업이 필요 합니다.  
  
 Uri 생성자에 문자열을 전달 하면 다음 URI가 발생 합니다.  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 경로를 해당 세그먼트로 분할 하면 다음 요소가 생성 됩니다.  
  
 `Customer('1`  
  
 `3812')`  
  
 이것은 요청을 보낸 사람의 의도가 아닙니다.  
  
 **UnescapeRequestUrl** 특성을 **false**로 설정 하면 <xref:System.Net.HttpListener> 요청을 받을 때 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 `http.sys`에서 변환 된 uri 대신 원시 uri를 사용 합니다.  
  
 **UnescapeRequestUrl** 특성의 기본값은 **true**입니다.  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 속성을 사용 하 여 적용 가능한 구성 파일에서 **unescapeRequestUrl** 특성의 현재 값을 가져올 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `http.sys`에서 변환 된 URI 대신 원시 URI를 사용 하 여 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대 한 입력으로 사용 하는 요청을 받을 때 <xref:System.Net.HttpListener> 클래스를 구성 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||
|-|-|  
|네임스페이스|System.Net|  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있음||  
  
## <a name="see-also"></a>참조

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [네트워크 설정 스키마](index.md)
