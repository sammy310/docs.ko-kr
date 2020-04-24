---
title: '방법: 게시자 정책 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646050"
---
# <a name="how-to-create-a-publisher-policy"></a>방법: 게시자 정책 만들기

어셈블리 공급업체는 응용 프로그램이 업그레이드된 어셈블리와 함께 게시자 정책 파일을 포함하여 최신 버전의 어셈블리를 사용해야 한다고 명시할 수 있습니다. 게시자 정책 파일은 어셈블리 리디렉션 및 코드 기본 설정을 지정하고 응용 프로그램 구성 파일과 동일한 형식을 사용합니다. 게시자 정책 파일은 어셈블리로 컴파일되어 전역 어셈블리 캐시에 배치됩니다.

게시자 정책을 만드는 데는 세 가지 단계가 있습니다.

1. 게시자 정책 파일을 만듭니다.

2. 게시자 정책 어셈블리를 만듭니다.

3. 전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가합니다.

게시자 정책에 대한 스키마는 [어셈블리 버전 리디렉션에 설명되어 있습니다.](redirect-assembly-versions.md) 다음 예제에서는 한 버전을 다른 버전으로 `myAssembly` 리디렉션하는 게시자 정책 파일을 보여 주습니다.

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

코드 베이스를 지정하는 방법을 알아보려면 [어셈블리의 위치 지정](specify-assembly-location.md)을 참조하십시오.

## <a name="creating-the-publisher-policy-assembly"></a>게시자 정책 어셈블리 만들기

[어셈블리 링커(Al.exe)를](../tools/al-exe-assembly-linker.md) 사용하여 게시자 정책 어셈블리를 만듭니다.

#### <a name="to-create-a-publisher-policy-assembly"></a>게시자 정책 어셈블리를 만들려면

명령 프롬프트에서 다음 명령을 입력합니다.

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

이 명령에서 다음이 적용됩니다.

- 인수는 `publisherPolicyFile` 게시자 정책 파일의 이름입니다.

- 인수는 `publisherPolicyAssemblyFile` 이 명령에서 발생하는 게시자 정책 어셈블리의 이름입니다. 어셈블리 파일 이름은 다음 형식을 따라야 합니다.

  '정책.주요번호.마이너넘버.메인어셈블리네임.dll'

- 인수는 `keyPairFile` 키 쌍을 포함하는 파일의 이름입니다. 동일한 키 쌍을 가진 어셈블리 및 게시자 정책 어셈블리에 서명해야 합니다.

- 인수는 `processorArchitecture` 프로세서 별 어셈블리의 대상 플랫폼을 식별합니다.

  > [!NOTE]
  > 특정 프로세서 아키텍처를 대상으로 지정하는 기능은 .NET Framework 2.0부터 사용할 수 있습니다.

특정 프로세서 아키텍처를 대상으로 지정하는 기능은 .NET Framework 2.0부터 사용할 수 있습니다. 다음 명령은 파일의 키 `policy.1.0.myAssembly` 쌍을 사용하여 어셈블리에 강력한 이름을 할당하고 어셈블리가 x86 프로세서 아키텍처를 대상으로 지정하도록 지정하는 게시자 `pub.config`정책 파일에서 호출된 게시자 정책 어셈블리를 `sgKey.snk` 만듭니다.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

게시자 정책 어셈블리는 적용되는 어셈블리의 프로세서 아키텍처와 일치해야 합니다. 따라서 어셈블리에 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> <xref:System.Reflection.ProcessorArchitecture.MSIL>값이 있는 경우 해당 어셈블리에 대한 `/platform:anycpu`게시자 정책 어셈블리를 으로 만들어야 합니다. 각 프로세서별 어셈블리에 대해 별도의 게시자 정책 어셈블리를 제공해야 합니다.

이 규칙의 결과는 어셈블리의 프로세서 아키텍처를 변경하려면 버전 번호의 주 또는 부 구성 요소를 변경하여 올바른 프로세서 아키텍처를 사용하여 새 게시자 정책 어셈블리를 제공해야 합니다. 어셈블리에 다른 프로세서 아키텍처가 있으면 이전 게시자 정책 어셈블리가 어셈블리를 서비스할 수 없습니다.

또 다른 결과는 항상 프로세서 아키텍처를 지정하기 때문에 버전 2.0 링커를 사용하여 .NET Framework의 이전 버전을 사용하여 컴파일된 어셈블리에 대한 게시자 정책 어셈블리를 만들 수 없습니다.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>전역 어셈블리 캐시에 게시자 정책 어셈블리 추가

전역 [어셈블리 캐시 도구(Gacutil.exe)를](../tools/gacutil-exe-gac-tool.md) 사용하여 전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가합니다.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가하려면

명령 프롬프트에서 다음 명령을 입력합니다.

```console
gacutil /i publisherPolicyAssemblyFile
```

다음 명령은 `policy.1.0.myAssembly.dll` 전역 어셈블리 캐시에 추가됩니다.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> `/link` 인수에 지정된 원래 게시자 정책 파일이 어셈블리와 동일한 디렉터리에 없으면 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 없습니다.

## <a name="see-also"></a>참고 항목

- [어셈블리를 사용한 프로그래밍](../../standard/assembly/index.md)
- [런타임에서 어셈블리를 찾는 방법](../deployment/how-the-runtime-locates-assemblies.md)
- [구성 파일을 사용하여 앱 구성](index.md)
- [런타임 설정 스키마](./file-schema/runtime/index.md)
- [구성 파일 스키마](./file-schema/index.md)
- [어셈블리 버전 리디렉션](redirect-assembly-versions.md)
