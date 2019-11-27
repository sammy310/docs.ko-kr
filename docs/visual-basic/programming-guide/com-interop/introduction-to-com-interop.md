---
title: COM Interop 소개
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: c7909b3b6a2c9f0b397b9621b7e5125c232be313
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353209"
---
# <a name="introduction-to-com-interop-visual-basic"></a>COM Interop 소개(Visual Basic)
COM (구성 요소 개체 모델)을 사용 하면 개체가 다른 구성 요소 및 호스트 응용 프로그램에 해당 기능을 노출할 수 있습니다. COM 개체는 대부분의 경우 Windows 프로그래밍에 대 한 기본 사항 이지만 CLR (공용 언어 런타임) 용으로 설계 된 응용 프로그램은 다양 한 이점을 제공 합니다.  
  
 .NET Framework 응용 프로그램은 궁극적으로 개발 된 응용 프로그램을 COM으로 바꿉니다. 그때까지 Visual Studio를 사용 하 여 COM 개체를 사용 하거나 만들어야 할 수 있습니다. COM 또는 *COM interop*와의 상호 운용성을 통해 사용자가 원하는 속도로 .NET Framework으로 전환 하는 동안 기존 com 개체를 사용할 수 있습니다.  
  
 .NET Framework를 사용 하 여 COM 구성 요소를 만들면 등록이 필요 없는 COM interop를 사용할 수 있습니다. 이렇게 하면 컴퓨터에 두 개 이상의 버전이 설치 되어 있을 때 사용할 수 있는 DLL 버전을 제어할 수 있으며, 최종 사용자는 XCOPY 또는 FTP를 사용 하 여 응용 프로그램을 실행할 수 있는 컴퓨터의 적절 한 디렉터리에 응용 프로그램을 복사할 수 있습니다. 자세한 내용은 [등록이 필요 없는 COM Interop](../../../framework/interop/registration-free-com-interop.md)를 참조 하세요.  
  
## <a name="managed-code-and-data"></a>관리 코드 및 데이터  
 .NET Framework 용으로 개발 된 코드를 *관리 코드*라고 하며 CLR에서 사용 하는 메타 데이터를 포함 합니다. 런타임에서 메모리 할당과 회수 및 형식 검사를 수행 하는 등의 데이터 관련 작업을 관리 하기 때문에 .NET Framework 응용 프로그램에서 사용 하는 데이터를 관리 되는 *데이터* 라고 합니다. 기본적으로 Visual Basic .NET은 관리 코드 및 데이터를 사용 하지만 interop 어셈블리를 사용 하 여 COM 개체의 비관리 코드 및 데이터에 액세스할 수 있습니다 (이 페이지 뒷부분에서 설명).  
  
## <a name="assemblies"></a>Assemblies  
 어셈블리는 .NET Framework 응용 프로그램의 기본 구성 요소입니다. 하나 이상의 파일을 포함 하는 단일 구현 단위로 빌드하고, 버전이 지정 되 고, 배포 되는 기능 모음입니다. 각 어셈블리는 어셈블리 매니페스트를 포함 합니다.  
  
## <a name="type-libraries-and-assembly-manifests"></a>형식 라이브러리 및 어셈블리 매니페스트  
 형식 라이브러리는 멤버 이름 및 데이터 형식과 같은 COM 개체의 특징을 설명 합니다. 어셈블리 매니페스트는 .NET Framework 응용 프로그램에 대해 동일한 기능을 수행 합니다. 여기에는 다음에 대 한 정보가 포함 됩니다.  
  
- 어셈블리 id, 버전, 문화권 및 디지털 서명입니다.  
  
- 어셈블리 구현을 구성 하는 파일입니다.  
  
- 어셈블리를 구성 하는 형식 및 리소스입니다. 여기에는 여기에서 내보낸 항목이 포함 됩니다.  
  
- 다른 어셈블리에 대 한 컴파일 타임 종속성.  
  
- 어셈블리를 올바르게 실행 하는 데 필요한 권한입니다.  
  
 어셈블리 및 어셈블리 매니페스트에 대 한 자세한 내용은 [.net의 어셈블리](../../../standard/assembly/index.md)를 참조 하세요.  
  
### <a name="importing-and-exporting-type-libraries"></a>형식 라이브러리 가져오기 및 내보내기  
 Visual Studio에는 형식 라이브러리의 정보를 .NET Framework 응용 프로그램으로 가져올 수 있는 Tlbimp 유틸리티인 Tlbimp가 포함 되어 있습니다. Tlbexp.exe 유틸리티를 사용 하 여 어셈블리에서 형식 라이브러리를 생성할 수 있습니다.  
  
 Tlbimp 및 Tlbexp.exe에 대 한 자세한 내용은 [tlbimp.exe (형식 라이브러리 가져오기)](../../../framework/tools/tlbimp-exe-type-library-importer.md) 및 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)를 참조 하세요.  
  
## <a name="interop-assemblies"></a>Interop 어셈블리  
 Interop 어셈블리는 관리 코드와 비관리 코드 간에 연결 되는 .NET Framework 어셈블리로, COM 개체 멤버를 동등한 .NET Framework 관리 되는 멤버에 매핑합니다. Visual Basic .NET에서 만든 Interop 어셈블리는 상호 운용성 마샬링을 비롯 한 COM 개체 작업에 대 한 많은 세부 정보를 처리 합니다.  
  
## <a name="interoperability-marshaling"></a>상호 운용성 마샬링  
 모든 .NET Framework 응용 프로그램은 사용 되는 프로그래밍 언어에 관계 없이 개체의 상호 운용성을 가능 하 게 하는 공용 형식 집합을 공유 합니다. COM 개체의 매개 변수 및 반환 값은 관리 코드에서 사용 되는 것과 다른 데이터 형식을 사용 하는 경우도 있습니다. *상호 운용성 마샬링은* COM 개체에서 이동 하는 것과 동일한 데이터 형식으로 매개 변수 및 반환 값을 패키징하는 프로세스입니다. 자세한 내용은 [Interop 마샬링](../../../framework/interop/interop-marshaling.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [비관리 코드와의 상호 운용](../../../framework/interop/index.md)
- [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Tlbimp.exe(형식 라이브러리 가져오기)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe(형식 라이브러리 내보내기)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [interop 마샬링](../../../framework/interop/interop-marshaling.md)
- [등록이 필요 없는 COM interop](../../../framework/interop/registration-free-com-interop.md)
