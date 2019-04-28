---
title: '방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: ac278123e9b0927ba6b2ce07059561e7fbb3a898
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605706"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="20a8f-102">방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="20a8f-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="20a8f-103">이 항목에서는 사용 하는 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) 모델 및 매핑 파일 유효성을 검사 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="20a8f-104">자세한 내용은 [엔터티 데이터 모델](../../../../../docs/framework/data/adonet/entity-data-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="20a8f-105">EdmGen.exe를 사용하여 School 모델의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="20a8f-105">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="20a8f-106">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-106">Create the School database.</span></span> <span data-ttu-id="20a8f-107">자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-107">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="20a8f-108">School 모델을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-108">Generate the School model.</span></span> <span data-ttu-id="20a8f-109">자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="20a8f-110">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20a8f-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="20a8f-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="20a8f-111">See also</span></span>

- <span data-ttu-id="20a8f-112">[방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="20a8f-112">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="20a8f-113">[ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="20a8f-113">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="20a8f-114">[방법: 쿼리 성능을 개선 하는 뷰를 미리 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="20a8f-114">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="20a8f-115">방법: EdmGen.exe를 사용 하 여 개체 계층 코드 생성</span><span class="sxs-lookup"><span data-stu-id="20a8f-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
