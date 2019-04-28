---
title: '방법: DEVPATH를 사용하여 어셈블리 찾기'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 5c4041f42b0a9d1d1e4bc8438e662911534daa42
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775832"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>방법: DEVPATH를 사용하여 어셈블리 찾기
개발자가 작성 하는 공유 어셈블리를 여러 응용 프로그램을 사용 하 여 올바르게 작동 하는지 확인 수 있습니다. 지속적으로 어셈블리를 전역 어셈블리 캐시에서 개발 주기 동안에 배치 하는 대신 개발자는 어셈블리에 대 한 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들면 됩니다.  
  
 출력 디렉터리는 C:\MySharedAssembly\Debug 고 예를 들어 MySharedAssembly 라는 공유 어셈블리를 작성할 수 있도록를 가정 합니다. C:\MySharedAssembly\Debug DEVPATH 변수에 넣을 수 있습니다. 지정 해야 합니다 [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) 컴퓨터 구성 파일의 요소입니다. 이 요소에는 공용 언어 런타임을 어셈블리를 찾는 데 DEVPATH를 사용 하도록 알려 줍니다.  
  
 공유 어셈블리는 런타임에서 검색할 수 있어야 합니다.  어셈블리 참조 사용을 확인 하기 위한 전용 디렉터리를 지정 하는 [ \<코드 베이스 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 하거나 [ \<검색 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 에 설명 된 대로 구성 파일에서 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.  또한 응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 넣을 수 있습니다. 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.  
  
> [!NOTE]
>  이것이 개발만을 위한 고급 기능입니다.  
  
 다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 이 설정의 기본값은 false입니다.  
  
> [!NOTE]
>  개발 타임에만이 설정을 사용 합니다. 런타임에서 DEVPATH에 있는 강력한 이름의 어셈블리의 버전을 확인 하지 않습니다. 단순히 찾은 첫 번째 어셈블리를 사용 합니다.  
  
## <a name="see-also"></a>참고자료

- [구성 파일을 사용 하 여 앱 구성](index.md)
