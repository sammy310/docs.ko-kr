---
title: WCF 및 IDN(Internationalized Domain Name)
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: c166f497117314dd8cea3b04b9b1072203374c52
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112608"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF 및 IDN(Internationalized Domain Name)
IDN(Internationalized Domain Name)을 사용하는 WCF 서비스에 대한 지원이 추가되었습니다. IDN(Internationalized Domain Name)은 비 ASCII 문자가 포함된 도메인 이름입니다. 이 지원을 통해 IDN 이름을 사용하는 WCF 서비스와 IDN 이름을 사용하는 웹 서비스와 통신하는 WCF 클라이언트를 둘 다 호스트할 수 있습니다.  
  
## <a name="systemuri-and-idn"></a>System.Uri 및 IDN  
 <xref:System.Uri> 두 속성이 <xref:System.Uri.Host%2A> 고 <xref:System.Uri.DnsSafeHost%2A>입니다. 이러한 속성에는 IDN 구성 설정에 따라 유니코드 또는 Punycode 값이 들어 있습니다.  
  
 IDN은 다음 XML을 사용하여 응용 프로그램의 구성 파일에서 사용할 수 있습니다.  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<idn > 요소에 다음 값 중 하나로 설정할 수 있는 사용된 특성이 포함 되어 있습니다.  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "All"  
  
 IDN 설정이 "None"으로 설정 되 면 Uri.Host 또는 Uri.DnsSafeHost에 의해 변환이 수행 됩니다. IDN 설정이 "All", uri로 설정 하면 합니다. 유니코드 및 uri 호스트에 유지 됩니다. DnsSafeHost은 Punycode로 변환 됩니다. IDN 설정이 "AllExceptIntranet", uri 설정 하면 합니다. DnsSafeHost은 인터넷 주소 용인 Punycode로 변환 됩니다 및 인트라넷 주소 용인 유니코드로 유지 됩니다. 이 설정은 정확한 DNS 이름 확인을 위해 중요합니다. Windows 8 및 최신 버전에서는 이 설정을 구성하지 않아도 됩니다.  
  
> [!WARNING]
>  Punycode를 사용하여 주소를 하드 코딩하지 마세요. WCF는 사용자가 적용하는 구성 설정을 기준으로 변환해 줍니다.  
  
> [!WARNING]
>  applicationHost.exe.config에 유니코드 문자를 추가하는 경우 파일을 UTF-8 인코딩으로 저장하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Uri?displayProperty=nameWithType>
