---
title: '방법: 게시자 정책 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: ce2df9d4cea601652ebde2032758137b01faacdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344665"
---
# <a name="how-to-create-a-publisher-policy"></a>방법: 게시자 정책 만들기
어셈블리 공급 업체는 응용 프로그램 업그레이드 된 어셈블리를 사용 하 여 게시자 정책 파일을 포함 하 여 최신 버전의 어셈블리를 사용할지는 상태 수입니다. 게시자 정책 파일 어셈블리 리디렉션 및 코드 베이스 설정을 지정 하 고 응용 프로그램 구성 파일로 동일한 형식을 사용 합니다. 게시자 정책 파일을 어셈블리로 컴파일되고 전역 어셈블리 캐시에 배치 됩니다.  
  
 게시자 정책 만들기와 관련 된 세 가지 단계는:  
  
1. 게시자 정책 파일을 만듭니다.  
  
2. 게시자 정책 어셈블리를 만듭니다.  
  
3. 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.  
  
 게시자 정책에 대 한 스키마에 설명 되어 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)합니다. 다음 예제에서는 게시자 정책 파일 버전으로 리디렉션하는 `myAssembly` 다른 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 코드 베이스를 지정 하는 방법에 알아보려면 참조 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.  
  
## <a name="creating-the-publisher-policy-assembly"></a>게시자 정책 어셈블리 만들기  
 사용 된 [어셈블리 링커 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 게시자 정책 어셈블리를 만들어야 합니다.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>게시자 정책 어셈블리를 만들려면  
  
1. 명령 프롬프트에서 다음 명령을 입력 합니다.  
  
     **al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*  
  
     이 명령:  
  
    -   합니다 *publisherPolicyFile* 인수는 게시자 정책 파일의 이름입니다.  
  
    -   합니다 *publisherPolicyAssemblyFile* 인수는이 명령에서 발생 하는 게시자 정책 어셈블리의 이름입니다. 어셈블리 파일 이름 형식을 따라야 합니다.  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   합니다 *keyPairFile* 인수는 키 쌍을 포함 하는 파일의 이름입니다. 어셈블리와 동일한 키 쌍을 사용 하 여 게시자 정책 어셈블리에 서명 해야 합니다.  
  
    -   합니다 *processorArchitecture* 인수 프로세서 특정 어셈블리의 대상 플랫폼을 식별 합니다.  
  
        > [!NOTE]
        >  특정 프로세서 아키텍처를 대상으로 하는 기능은.NET Framework 버전 2.0의에서 새로운 기능입니다.  
  
     명령을 호출 하는 게시자 정책 어셈블리를 만듭니다 `policy.1.0.myAssembly` 게시자 정책 파일에서 호출 `pub.config`에 있는 키 쌍을 사용 하 여 어셈블리에 강력한 이름을 할당 합니다 `sgKey.snk` 파일과 어셈블리는 x86 대상으로 지정 함을 지정 합니다. 프로세서 아키텍처입니다.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     게시자 정책 어셈블리에 적용 되는 어셈블리의 프로세서 아키텍처를 일치 해야 합니다. 따라서 어셈블리에 있는 경우는 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> 의 값 <xref:System.Reflection.ProcessorArchitecture.MSIL>를 사용 하 여 해당 어셈블리에 대 한 게시자 정책 어셈블리를 만들어야 합니다 `/platform:anycpu`합니다. 별도 변경 하면 각 프로세서 특정 어셈블리에 대 한 게시자 정책 어셈블리입니다.  
  
     이 규칙에 따른은 어셈블리의 프로세서 아키텍처를 변경 하기 위해 버전 번호의 주 또는 부 버전 구성 요소 변경 해야 하므로 올바른 프로세서 아키텍처를 사용 하는 새 게시자 정책 어셈블리를 제공할 수 있습니다. 어셈블리에는 다른 프로세서 아키텍처 이전 게시자 정책 어셈블리에서 어셈블리를 처리할 수 없습니다.  
  
     다른 결과 항상 프로세서 아키텍처를 지정 하기 때문에 이전 버전의.NET Framework를 사용 하 여 컴파일된 어셈블리에 대 한 게시자 정책 어셈블리를 만드는 버전 2.0 링커를 사용할 수 없습니다.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가  
 사용 된 [전역 어셈블리 캐시 도구 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 하려면  
  
1. 명령 프롬프트에서 다음 명령을 입력 합니다.  
  
     **gacutil /i**  *publisherPolicyAssemblyFile*  
  
     다음 명령을 추가 `policy.1.0.myAssembly.dll` 전역 어셈블리 캐시에 있습니다.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  원래 게시자 정책 파일이 어셈블리와 동일한 디렉터리에 위치한 하지 않는 한 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 없습니다.  
  
## <a name="see-also"></a>참고자료

- [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [구성 파일을 사용 하 여 앱 구성](../../../docs/framework/configure-apps/index.md)
- [런타임 설정 스키마](../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)
- [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
