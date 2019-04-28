---
title: 이미지를 보다 쉽게.NET에서 디버그
description: 전환 IDE를 사용 하 여 보다 쉽게 디버깅에 대 한 실행 가능 이미지를 구성 하는 방법 및 명령줄 옵션에 알아봅니다.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bab707afb059d4fcbd46a9ee54edead991be523
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754221"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>이미지를 보다 쉽게.NET에서 디버그

비관리 코드를 컴파일할 때 IDE 스위치 또는 명령줄 옵션을 설정하여 디버깅할 실행 가능 이미지를 구성할 수 있습니다. 예를 들어 Visual C++에서 /**Zi** 명령줄 옵션을 사용하여 디버그 기호 파일(확장 확장자는 .pdb)을 생성하도록 요청할 수 있습니다. 마찬가지로 /**Od** 명령줄 옵션을 사용하면 최적화를 사용하지 않게 설정하도록 컴파일러에 지시합니다. 결과 코드는 더 느리게 실행 이지만 쉽게 디버깅을 수행할 수 있습니다.

관리 코드, 시각적 개체와 같은 컴파일러.NET Framework를 컴파일할 때 C++, Visual Basic 및 C# MSIL (Microsoft intermediate language)로 소스 프로그램을 컴파일합니다. 그런 다음 MSIL이 JIT 컴파일된 네이티브 기계어 코드로 실행 직전. 비관리 코드와 함께 IDE 스위치 또는 명령줄 옵션을 설정하여 디버깅할 실행 가능 이미지를 구성할 수 있습니다. 또한 동일한 방식으로 디버깅을 위해 JIT 컴파일을 구성할 수 있습니다.

JIT 구성에는 두 가지 요소가 있습니다.

- 추적 정보를 생성 하려면 JIT 컴파일러를 요청할 수 있습니다. 그러면 디버거에서 MSIL 체인을 대응하는 기계어 코드와 일치시키고 지역 변수와 함수 인수가 저장된 위치를 추적할 수 있습니다. .NET Framework 버전 2.0부터 JIT 컴파일러가 항상 생성 추적 정보를 하므로 요청할 필요가 없습니다.

- 결과 기계어 코드를 최적화 하지 JIT 컴파일러를 요청할 수 있습니다.

일반적으로 MSIL을 생성 하는 컴파일러 JIT 컴파일러 옵션 설정 적절 하 게 IDE 스위치 또는 예를 들어 지정 하는 명령줄 옵션에 따라 /**Od**합니다.

경우에 따라 생성되는 기계어 코드를 더 쉽게 디버깅할 수 있도록 JIT 컴파일러의 동작을 변경하는 것이 좋습니다. 예를 들어, 정품 빌드 또는 제어 최적화를 위해 JIT 추적 정보를 생성할 수 있습니다. 초기화(.ini) 파일을 사용해서도 수행할 수 있습니다.

예를 들어, 디버깅 하려는 어셈블리 라고 *MyApp.exe*, 라는 텍스트 파일을 만들 수 있습니다 *MyApp.ini*를 동일한 폴더에 *MyApp.exe*를 포함 하는 이러한 세 줄:

```ini
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

각 옵션의 값은 0 또는 1로 설정되고 비어 있는 옵션은 기본값으로 0으로 설정됩니다. `GenerateTrackingInfo`를 1로 설정하고 `AllowOptimize`를 0으로 설정하면 디버깅이 가장 쉬워집니다.

.NET Framework 버전 2.0부터 JIT 컴파일러는 항상 생성에 대 한 값에 관계 없이 추적 정보 `GenerateTrackingInfo`있지만 `AllowOptimize` 값은 여전히 영향을 미칩니다. [Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 사용하여 최적화하지 않고 네이티브 이미지를 사전 컴파일하는 경우 Ngen.exe가 실행될 때 `AllowOptimize=0`인 대상 폴더에 .ini 파일이 있어야 합니다. 최적화 하지 않고 어셈블리를 미리 컴파일한 경우 NGen.exe를 사용 하 여 미리 컴파일된 코드를 제거 해야 **제거 /** Ngen.exe를 다시 실행 하기 전에 코드를 미리 컴파일하는 최적화 된 상태로 옵션입니다. .Ini 파일 폴더에 없으면 기본적으로 Ngen.exe 코드를 사전 컴파일합니다 최적화 때문입니다.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType>을 통해 어셈블리의 설정을 제어합니다. **DebuggableAttribute** JIT 컴파일러 최적화 하거나 추적 정보를 생성 해야 하는지 여부를 제어 하는 두 개의 필드가 포함 됩니다. 추적 정보는 JIT 컴파일러에서 항상 생성는.NET Framework 버전 2.0부터 합니다.

일반 정품 빌드에 대 한 컴파일러 설정 하지 않습니다 모든 **DebuggableAttribute**합니다. 기본적으로 JIT 컴파일러는 최고 성능을 위해 기계어 코드를 디버그 하기 어렵습니다를 생성 합니다. JIT 추적을 사용하면 성능이 약간 저하되지만 최적화를 사용하지 않게 설정하면 성능이 상당히 저하됩니다.

**DebuggableAttribute**는 어셈블리에 있는 개별 모듈이 아니라 한 번에 전체 어셈블리에 적용됩니다. 따라서 개발 도구에서 사용자 지정 특성을 어셈블리 메타데이터 토큰에 연결하거나, 어셈블리가 이미 생성된 경우 **System.Runtime.CompilerServices.AssemblyAttributesGoHere**라는 클래스에 연결해야 합니다. ALink 도구가 이러한 것도 승격 됩니다 **DebuggableAttribute** 어셈블리에 각 모듈에서 특성은의 일부가 됩니다. 충돌 하는 경우 ALink 작업이 실패 합니다.

> [!NOTE]
> .NET Framework 버전 1.0에서 **/clr** 및 **/Zi** 컴파일러 옵션이 지정된 경우 Microsoft Visual C++ Compiler에서 **DebuggableAttribute**를 추가합니다. .NET Framework 버전 1.1에서에서 추가 하거나 합니다 **DebuggableAttribute** 코드나 사용 하 여 프로그램에서 수동으로 합니다 **/ASSEMBLYDEBUG** 링커 옵션.

## <a name="see-also"></a>참고자료

- [디버깅, 추적 및 프로파일링](../../../docs/framework/debug-trace-profile/index.md)
- [JIT 연결 디버깅 설정](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)
- [프로파일링 설정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
