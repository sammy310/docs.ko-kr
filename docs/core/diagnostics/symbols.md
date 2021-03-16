---
title: .NET의 기호
description: .NET의 기호 및 이식 가능한 PDB 소개
ms.date: 02/08/2021
ms.openlocfilehash: da59a07166cd1f73160da8d9ac53b5823bf13e7b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108379"
---
# <a name="symbols"></a>기호

기호는 디버깅 및 기타 진단 도구에 유용합니다. 기호 파일의 콘텐츠는 언어, 컴파일러, 플랫폼마다 다릅니다. 아주 높은 수준에서 기호는 컴파일러에 의해 생성된 소스 코드와 이진 간의 매핑입니다. 해당 매핑은 [Visual Studio](/visualstudio/debugger/what-is-debugging) 및 [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) 같은 도구에서 소스 줄 번호 정보 또는 지역 변수 이름을 확인하는 데 사용됩니다.

많은 개념이 다른 플랫폼에도 적용되지만 [기호에 관한 Windows 설명서](/windows/win32/dxtecharts/debugging-with-symbols)에는 Windows용 기호에 관한 자세한 정보가 포함되어 있습니다.

## <a name="learn-about-nets-portable-pdb-format"></a>.NET의 이식 가능한 PDB 형식에 관한 자세한 정보

.NET Core에는 이식 가능한 PDB인 새 기호 파일(PDB) 형식이 도입됩니다. Windows 전용인 기존 PDB와는 달리, 이식 가능한 PDB는 모든 플랫폼에서 만들고 읽을 수 있습니다.

### <a name="what-is-a-pdb"></a>PDB란?

PDB 파일은 컴파일러에서 주 실행 파일의 콘텐츠 및 해당 콘텐츠의 생성 방식에 관한 정보를 다른 도구, 특히 디버거에 제공하기 위해 생성되는 보조 파일입니다. 예를 들어, 디버거는 PDB를 읽어서 foo.cs 줄 12를 올바른 실행 파일 위치에 매핑하므로 중단점을 설정할 수 있습니다. Windows PDB 형식은 오랫동안 사용되었으며 훨씬 더 오래된 다른 네이티브 디버깅 기호 형식에서 진화했습니다. 해당 형식은 네이티브(C/C++) 프로그램의 형식으로 사용되기 시작했습니다. .NET Framework의 첫 번째 릴리스에서 Windows PDB 형식은 .NET을 지원하도록 확장되었습니다.

## <a name="use-the-correct-pdb-format-for-your-scenario"></a>시나리오에 올바른 PDB 형식 사용

이식 가능한 PDB와 Windows PDB는 둘 다 모든 곳에서 지원되지 않으므로 사용할 형식을 결정하기 위해 프로젝트를 사용하고 디버그할 위치를 고려해야 합니다. 두 형식에서 모두 사용하고 디버그할 수 있는 프로젝트가 있는 경우 다른 빌드 구성을 사용하고 프로젝트를 두 번 빌드하여 두 유형의 소비자를 지원할 수 있습니다.

### <a name="support-for-portable-pdbs"></a>이식 가능한 PDB 지원

이식 가능한 PDB는 모든 운영 체제에서 읽을 수 있으며 관리 코드에 권장되는 기호 형식이지만, 해당 형식이 지원되지 않는 많은 레거시 도구와 애플리케이션이 있습니다.

* .NET Framework 4.7.1 이하를 대상으로 하는 애플리케이션: 인쇄 스택은 줄 번호로 역방향 매핑을 사용하여 추적합니다(예: ASP.NET 오류 페이지에서). 메서드 이름은 영향을 받지 않으며 소스 파일 이름과 줄 번호만 지원되지 않습니다.

* ildasm.exe 또는 .NET 리플렉터와 같은 .NET 디컴파일러를 사용하여 소스 줄 매핑 또는 지역 매개 변수 이름을 확인합니다.

* WinDBG와 같은 기호를 읽는 데 사용하는 최신 버전의 [DIA](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk) 및 도구는 이식 가능한 PDB를 지원하지만 이전 버전은 지원하지 않습니다.

* 이식 가능한 PDB를 지원하지 않는 이전 버전의 프로파일러가 있을 수 있습니다.

이식 가능한 PDB를 지원하지 않는 도구에서 해당 형식을 사용하려면 이식 가능한 PDB와 Windows PDB 간에 변환되는 Pdb2Pdb[https://github.com/dotnet/symreader-converter#pdb2pdb ]를 사용해 보세요.

### <a name="support-for-windows-pdbs"></a>Windows PDB 지원

Windows PDB는 Windows에서만 쓰거나 읽을 수 있습니다. 관리 코드에 Windows PDB를 사용하는 기능은 사용 중단되었으며 레거시 도구에만 필요합니다. 이식 가능한 PDB용으로만 구현되는 일부 최신 컴파일러 기능인 Windows PDB 대신 이식 가능한 PDB를 사용하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

* [dotnet-symbol](./dotnet-symbol.md)을 사용하여 프레임워크 이진의 기호 파일을 다운로드할 수 있음

* [기호에 관한 Windows 설명서](/windows/win32/dxtecharts/debugging-with-symbols)
