---
title: '방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: a5e3124eb907b8077df7db4d71240f6e6b7bae63
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544507"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사
이 항목에서는 [EDM 생성기 (EdmGen.exe)](edm-generator-edmgen-exe.md) 도구를 사용 하 여 모델 및 매핑 파일의 유효성을 검사 하는 방법을 보여 줍니다. 자세한 내용은 [엔터티 데이터 모델](../entity-data-model.md)를 참조 하세요.  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>EdmGen.exe를 사용하여 School 모델의 유효성을 검사하려면  
  
1. School 데이터베이스를 만듭니다. 자세한 내용은 [School 샘플 데이터베이스 만들기](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))를 참조 하세요.  
  
2. School 모델을 생성합니다. 자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조 하세요.  
  
3. 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>참조

- [방법: 수동으로 Entity Framework 프로젝트 구성](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [방법: 뷰를 미리 생성하여 쿼리 성능 향상](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [방법: EdmGen.exe를 사용하여 개체 계층 코드 생성](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
