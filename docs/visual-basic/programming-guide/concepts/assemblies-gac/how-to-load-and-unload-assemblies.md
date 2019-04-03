---
title: '방법: 어셈블리 로드 및 언로드 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
ms.openlocfilehash: 07c8370d7aeb5171f991ddf24bf473f787408f2d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838770"
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>방법: 어셈블리 로드 및 언로드 (Visual Basic)
프로그램에서 참조하는 어셈블리는 빌드 시 자동으로 로드되지만, 런타임에 현재 애플리케이션 도메인에 특정 어셈블리를 로드할 수도 있습니다. 자세한 내용은 [방법: 애플리케이션 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.  
  
 해당 어셈블리가 포함된 애플리케이션 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다. 어셈블리가 범위를 벗어난 경우에도 실제 어셈블리 파일은 해당 파일을 포함하는 애플리케이션 도메인이 모두 언로드될 때까지 로드된 상태로 유지됩니다.  
  
 일부 어셈블리만 언로드하고 다른 어셈블리는 언로드하지 않으려는 경우 새 애플리케이션 도메인을 만들고, 이 도메인 내에서 코드를 실행한 다음 해당 애플리케이션 도메인을 언로드하는 것이 좋습니다. 자세한 내용은 [방법: 애플리케이션 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>애플리케이션 도메인에 어셈블리를 로드하려면  
  
1.  <xref:System.AppDomain> 및 <xref:System.Reflection> 클래스에 포함된 여러 로드 메서드 중 하나를 사용합니다. 자세한 내용은 [방법: 애플리케이션 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.  
  
### <a name="to-unload-an-application-domain"></a>애플리케이션 도메인을 언로드하려면  
  
1.  해당 어셈블리가 포함된 애플리케이션 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다. <xref:System.AppDomain>의 `Unload` 메서드를 사용하여 응용 프로그램 도메인을 언로드합니다. 자세한 내용은 [방법: 애플리케이션 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)
- [.NET 어셈블리](../../../../standard/assembly/index.md)
- [방법: 애플리케이션 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
