---
title: 어셈블리 위치 지정
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: f7d09e315f2ccc7ecdcf22719ca6dce1ee1411b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186292"
---
# <a name="specifying-an-assemblys-location"></a>어셈블리 위치 지정
두 가지 방법으로 어셈블리의 위치를 지정할 수 있습니다.  
  
-   사용 하는 [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 요소입니다.  
  
-   사용 하 여 [ \<검색 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 요소입니다.  
  
 사용할 수도 있습니다는 [.NET Framework 구성 도구 (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) 어셈블리 위치를 지정 하거나 어셈블리를 조사 하려면 공용 언어 런타임에 대 한 위치를 지정 합니다.  
  
## <a name="using-the-codebase-element"></a>사용 하 여 \<코드 베이스 > 요소  
 사용할 수는  **\<codeBase >** 어셈블리 버전을 리디렉션하는 컴퓨터 구성 또는 게시자 정책 파일에만 요소. 런타임에서 어셈블리 버전을 사용 하 여 결정을 하는 경우 버전을 결정 하는 파일에서 코드 베이스 설정을 적용 합니다. 없는 코드 베이스를 지정 하는 경우 런타임에서 일반적인 방법으로 어셈블리를 검색 합니다. 자세한 내용은 참조 하세요 [런타임 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.  
  
 다음 예제에서는 어셈블리의 위치를 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 합니다 **버전** 특성 모든 강력한 이름의 어셈블리에 대 한 필요 하지만 강력한 이름이 아닌 어셈블리에 대 한 생략 해야 합니다.  **\<코드 베이스 >** 요소에 필요 합니다 **href** 특성입니다. 에서는 버전 범위를 지정할 수 없습니다는  **\<codeBase >** 요소입니다.  
  
> [!NOTE]
>  강력한 이름이 없는 어셈블리에 대 한 코드 베이스 힌트를 제공 하는 경우 힌트는 응용 프로그램 기준 위치 또는 응용 프로그램 기본 디렉터리의 하위 디렉터리를 가리켜야 합니다.  
  
## <a name="using-the-probing-element"></a>사용 하 여 \<검색 > 요소  
 런타임이 검색 하 여 코드 베이스를 갖지 않는 어셈블리를 찾습니다. 검색에 대 한 자세한 내용은 참조 하세요. [런타임 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.  
  
 사용할 수는 [ \<검색 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 어셈블리를 찾을 때 런타임에서 검색 해야 하는 하위 디렉터리를 지정 하는 응용 프로그램 구성 파일의 요소입니다. 다음 예제에서는 런타임에서 검색 해야 하는 디렉터리를 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 합니다 **privatePath** 특성 런타임에서 어셈블리에 대 한 검색 해야 하는 디렉터리를 포함 합니다. 응용 프로그램이 C:\Program Files\MyApp에 있는 경우 런타임에서 C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin 및 C:\Program Files\MyApp\Bin3 코드 베이스를 지정 하지 않는 어셈블리를 찾습니다. 에 지정 된 디렉터리가 **privatePath** 응용 프로그램 기본 디렉터리의 하위 디렉터리 여야 합니다.  
  
## <a name="see-also"></a>참고자료

- [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [구성 파일을 사용하여 앱 구성](index.md)
