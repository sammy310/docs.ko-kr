---
title: '방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 915a9f3c53dba355480a3869602f963b195d53fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323800"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 생성
이 항목에서는 EDM 생성기(EdmGen.exe) 도구를 사용하여 School 데이터베이스를 기반으로 하는 다음 파일을 생성하는 방법을 보여 줍니다.  
  
-   개념적 모델(.csdl 파일)  
  
-   저장소 모델(.ssdl 파일)  
  
-   개념적 모델과 저장소 모델 간의 매핑(.msl 파일)  
  
-   Visual Basic 또는 C#의 개체 계층 코드  
  
-   뷰 파일  
  
 EdmGen.exe 도구에서는 /mode:FullGeneration을 사용하여 위에 나열된 파일을 생성합니다. EdmGen.exe 명령에 대 한 자세한 내용은 참조 하십시오 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)합니다.  
  
 EdmGen.exe를 사용 하 여 모델 및 매핑 파일을 생성 하는 경우 여전히 구성 해야 사용 하도록 Visual Studio 프로젝트는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 [방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))합니다.  
  
> [!NOTE]
>  EdmGen.exe에서 생성된 개념적 모델에는 데이터베이스의 모든 개체가 포함됩니다. 특정 개체만 포함된 개념적 모델을 생성하려면 엔터티 데이터 모델 마법사를 사용합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사를 사용 하 여](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))입니다.  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델을 생성하려면  
  
1. School 데이터베이스를 만듭니다. 자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))합니다.  
  
2. 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 C# 프로젝트용 School 모델을 생성하려면  
  
1. School 데이터베이스를 만듭니다. 자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))합니다.  
  
2. 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>참고자료

- [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [방법: 쿼리 성능을 개선 하는 뷰를 미리 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 유효성을 검사 하려면](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
