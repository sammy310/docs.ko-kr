---
title: 어셈블리 배치
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9b8357be5b9f49569114cbc1c2942eea03696eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180182"
---
# <a name="assembly-placement"></a>어셈블리 배치
대부분의 .NET Framework 애플리케이션의 경우 해당 애플리케이션을 구성하는 어셈블리는 애플리케이션 디렉터리, 애플리케이션 디렉터리의 하위 디렉터리 또는 전역 어셈블리 캐시(어셈블리가 공유된 경우)에서 찾을 수 있습니다. 구성 파일에 있는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하면 공용 언어 런타임에서 어셈블리를 검색하는 위치를 재정의할 수 있습니다. 어셈블리에 강력한 이름이 없는 경우, [\<codeBase&gt; 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 지정한 위치는 애플리케이션 디렉터리와 그 하위 디렉터리로 제한됩니다. 반면, 강력한 이름의 어셈블리인 경우에는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 컴퓨터 또는 네트워크상의 모든 위치를 지정할 수 있습니다.  
  
 비관리 코드나 COM interop 애플리케이션에 대해 어셈블리의 위치를 검색할 때도 이와 비슷한 규칙이 적용됩니다. 여러 애플리케이션에서 해당 어셈블리를 공유해야 하는 경우에는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다. 비관리 코드에 사용되는 어셈블리는 형식 라이브러리로 내보낸 후 등록해야 합니다. COM interop에 사용되는 어셈블리는 카달로그에 등록해야 하는데, 경우에 따라서는 어셈블리가 자동으로 등록됩니다.  
  
## <a name="see-also"></a>참고 항목

- [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [앱 구성](../../../docs/framework/configure-apps/index.md)
- [비관리 코드와의 상호 운용](../../../docs/framework/interop/index.md)
- [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
