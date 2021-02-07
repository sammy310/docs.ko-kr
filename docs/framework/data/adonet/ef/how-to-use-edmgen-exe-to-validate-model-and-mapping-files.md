---
description: '자세히 알아보기: 방법: 모델 및 매핑 파일의 유효성을 검사 하는 EdmGen.exe 사용'
title: '방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: e729ea36b7ff17dc318f4488a669b968161aea8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697350"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="607c4-103">방법: EdmGen.exe를 사용하여 모델 및 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="607c4-103">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>

<span data-ttu-id="607c4-104">이 항목에서는 [EDM 생성기 (EdmGen.exe)](edm-generator-edmgen-exe.md) 도구를 사용 하 여 모델 및 매핑 파일의 유효성을 검사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="607c4-104">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="607c4-105">자세한 내용은 [엔터티 데이터 모델](../entity-data-model.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="607c4-105">For more information, see [Entity Data Model](../entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="607c4-106">EdmGen.exe를 사용하여 School 모델의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="607c4-106">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="607c4-107">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="607c4-107">Create the School database.</span></span> <span data-ttu-id="607c4-108">자세한 내용은 [School 샘플 데이터베이스 만들기](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="607c4-108">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="607c4-109">School 모델을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="607c4-109">Generate the School model.</span></span> <span data-ttu-id="607c4-110">자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="607c4-110">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="607c4-111">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="607c4-111">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="607c4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="607c4-112">See also</span></span>

- <span data-ttu-id="607c4-113">[방법: 수동으로 Entity Framework 프로젝트 구성](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="607c4-113">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="607c4-114">[ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="607c4-114">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="607c4-115">[방법: 뷰를 미리 생성하여 쿼리 성능 향상](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="607c4-115">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="607c4-116">방법: EdmGen.exe를 사용하여 개체 계층 코드 생성</span><span class="sxs-lookup"><span data-stu-id="607c4-116">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
