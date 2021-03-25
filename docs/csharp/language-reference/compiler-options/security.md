---
description: 보안에 대한 C# 컴파일러 옵션입니다. 이러한 옵션은 서명 어셈블리 또는 주소 공간 레이아웃을 제어합니다.
title: C# 컴파일러 옵션 - 보안 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- PublicSign compiler option [C#]
- DelaySign compiler option [C#]
- KeyFile compiler option [C#]
- KeyContainer compiler option [C#]
- HighEntropyVA compiler option [C#]
ms.openlocfilehash: db7b612fa2e4ddb566ac2ba5ef9e4e66c5f0b0ab
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482437"
---
# <a name="c-compiler-options-for-security-options"></a>보안 옵션에 대한 C# 컴파일러 옵션

다음 옵션은 컴파일러 보안 옵션을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **PublicSign** / `-publicsign`: 어셈블리에 공개적으로 서명합니다.
- **DelaySign** / `-delaysign`: 강력한 이름 키의 공개 부분만 사용하여 어셈블리 서명을 연기합니다.
- **KeyFile** / `-keyfile`: 강력한 이름 키 파일을 지정합니다.
- **KeyContainer** / `-keycontainer`: 강력한 이름 키 컨테이너를 지정합니다.
- **HighEntropyVA** / `-highentropyva`: 높은 엔트로피 ASLR(Address Space Layout Randomization) 사용

## <a name="publicsign"></a>PublicSign

이 옵션을 사용하면 컴파일러가 공개 키를 적용하지만 실제로 어셈블리에 서명하지는 않습니다. 또한 **PublicSign** 옵션은 파일이 서명되었음을 런타임에 알리는 비트를 어셈블리에 설정합니다.

```xml
<PublicSign>true</PublicSign>
```

**PublicSign** 옵션에는 [**KeyFile**](#keyfile) 또는 [**KeyContainer**](#keycontainer)를 사용해야 합니다. **keyFile** 또는 **KeyContainer** 옵션은 공개 키를 지정합니다. **PublicSign** 및 **PublicSign** 옵션은 함께 사용할 수 없습니다. “모조 서명” 또는 “OSS 서명”이라고도 하는 퍼블릭 서명은 출력 어셈블리에 공개 키를 포함하고 “서명된” 플래그를 설정합니다. 퍼블릭 서명은 실제로 프라이빗 키를 사용하여 어셈블리에 서명하지 않습니다. 개발자는 오픈 소스 프로젝트에 공용 기호를 사용합니다.  사용자는 어셈블리에 서명하는 데 사용되는 프라이빗 키에 액세스할 수 없는 경우 릴리스된 "완전히 서명된" 어셈블리와 호환되는 어셈블리를 빌드합니다. 어셈블리가 완전히 서명되었는지 실제로 확인해야 하는 소비자는 거의 없으므로 완전히 서명된 어셈블리가 사용되는 거의 모든 시나리오에서 이러한 공개적으로 빌드된 어셈블리를 사용할 수 있습니다.

## <a name="delaysign"></a>DelaySign

이 옵션을 사용하면 나중에 디지털 시그니처를 추가할 수 있도록 컴파일러가 출력 파일에 공간을 예약합니다.

```xml
<DelaySign>true</DelaySign>
```

완전히 서명된 어셈블리가 필요하면 **DelaySign-** 을 사용합니다. 어셈블리에 공개 키만 배치하려면 **DelaySign** 을 사용합니다. **DelaySign** 옵션은 [**KeyFile**](#keyfile) 또는 [**KeyContainer**](#keycontainer)와 함께 사용하지 않으면 효과가 없습니다. [**KeyContainer**](#keycontainer) 및 [**PublicSign**](#publicsign) 옵션은 함께 사용할 수 없습니다. 완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다. 해당 작업을 통해 매니페스트가 포함된 파일에 저장된 디지털 서명이 생생됩니다. 어셈블리에 서명이 지연되면 컴파일러는 서명을 컴퓨팅하고 저장하지 않습니다. 대신 컴파일러는 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.

예를 들어 **DelaySign** 을 사용하면 테스터를 통해 전역 캐시에 어셈블리를 넣을 수 있습니다. 테스트를 마친 후 [어셈블리 링커](../../../framework/tools/al-exe-assembly-linker.md) 유틸리티를 통해 어셈블리에 프라이빗 키를 배치하여 어셈블리에 완전히 서명할 수 있습니다. 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.

## <a name="keyfile"></a>KeyFile

암호화 키를 포함하는 파일 이름을 지정합니다.

```xml
<KeyFile>filename</KeyFile>
```

`file`은 강력한 이름 키를 포함하는 파일의 이름입니다. 이 옵션을 사용하면 컴파일러는 지정된 파일의 퍼블릭 키를 어셈블리 매니페스트에 삽입한 다음 프라이빗 키를 사용하여 최종 어셈블리에 서명합니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. [ **-target:module**](output.md#targettype)로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [**AddModules**](inputs.md#addmodules)로 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다. [**Keycontainer**](#keycontainer)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [**DelaySign**](#delaysign)을 사용합니다. **KeyFile** 및 **KeyContainer** 가 모두 동일한 컴파일에 지정되면 컴파일러는 먼저 키 컨테이너를 찾습니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 컴파일러가 키 컨테이너를 찾지 못하면 [**KeyFile**](#keyfile)로 지정된 파일을 찾습니다. 해당 파일을 찾으면 어셈블리가 키 파일의 정보로 서명되고 키 정보가 키 컨테이너에 설치됩니다. 다음 컴파일에서 키 컨테이너가 유효합니다. 키 파일에는 공개 키만 포함될 수 있습니다. 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.

## <a name="keycontainer"></a>KeyContainer

암호화 키 컨테이너의 이름을 지정합니다.

```xml
<KeyContainer>container</KeyContainer>
```

`container`는 강력한 이름 키 컨테이너의 이름입니다. **KeyContainer** 옵션을 사용하면 컴파일러는 공유 가능한 구성 요소를 만듭니다. 컴파일러는 지정된 컨테이너의 퍼블릭 키를 어셈블리 매니페스트에 삽입하고 프라이빗 키를 사용하여 최종 어셈블리에 서명합니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. `sn -i`는 컨테이너에 키 쌍을 설치합니다. 이 옵션은 컴파일러가 CoreCLR에서 실행되는 경우 지원되지 않습니다. CoreCLR에서 빌드할 때 어셈블리에 서명하려면 [**KeyFile**](#keyfile) 옵션을 사용합니다. [**TargetType**](output.md#targettype)으로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [**AddModules**](inputs.md#addmodules)를 사용하여 이 모듈을 어셈블리로 컴파일할 때 어셈블리에 통합됩니다. MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>)으로 지정할 수도 있습니다. [**KeyFile**](#keyfile)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. [**DelaySign**](#delaysign)을 사용하여 공개 키를 어셈블리 매니페스트에 추가하지만 테스트가 완료될 때까지 어셈블리에 서명합니다. 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.

## <a name="highentropyva"></a>HighEntropyVA

**HighEntropyVA** 컴파일러 옵션은 특정 실행 파일이 높은 엔트로피 ASLR(Address Space Layout Randomization)을 지원하는지 여부를 Windows 커널에 알려줍니다.

```xml
<HighEntropyVA>true</HighEntropyVA>
```

이 옵션은 [**PlatformTarget**](output.md#platformtarget) 컴파일러 옵션으로 표시된 실행 파일이나 64비트 실행 파일이 높은 엔트로피 가상 주소 공간을 지원하도록 지정합니다. 이 옵션은 기본적으로 비활성화되어 있습니다. **HighEntropyVA** 를 사용하여 활성화합니다.

**HighEntropyVA** 옵션을 사용하면 Windows 커널의 호환되는 버전에서 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의로 선택할 때 보다 높은 수준의 엔트로피를 사용할 수 있습니다. 더 높은 수준의 엔트로피를 사용하면 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다. 따라서 특정 메모리 영역의 위치를 추측하기가 어려워집니다. **HighEntropyVA** 컴파일러 옵션에는 대상 실행 파일이 필요하며, 64비트 프로세스로 실행될 때 4GB(기가바이트)보다 큰 포인터 값을 처리할 수 있어야 합니다.
