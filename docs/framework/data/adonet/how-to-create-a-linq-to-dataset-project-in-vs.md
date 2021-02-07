---
description: '자세한 정보: 방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기'
title: Visual Studio에서 LINQ to DataSet 프로젝트 만들기
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 4ab626ddaa27780759df95462faac366be8beeff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723831"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="2524c-103">방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2524c-103">How to: Create a LINQ to DataSet project in Visual Studio</span></span>

<span data-ttu-id="2524c-104">LINQ 프로젝트의 다양한 형식에는 특정 어셈블리 참조 및 가져온 네임 스페이스 (Visual Basic)를 사용하거나 지시문 (C#)을 [사용](../../../csharp/language-reference/keywords/using-directive.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-104">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="2524c-105">LINQ의 최소 요구 사항은 *System.Core.dll* 에 대 한 참조 및 `using` 에 대 한 지시문입니다 <xref:System.Linq> .</span><span class="sxs-lookup"><span data-stu-id="2524c-105">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="2524c-106">이러한 요구 사항은 Visual Studio 2017 이상 버전에서 새 c # 콘솔 응용 프로그램 프로젝트를 만드는 경우 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-106">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017 or a later version.</span></span> <span data-ttu-id="2524c-107">이전 버전의 Visual Studio에서 프로젝트를 업그레이드 하는 경우 이러한 LINQ 관련 참조를 직접 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-107">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="2524c-108">LINQ to DataSet *System.Data.dll* 및 *System.Data.DataSetExtensions.dll* 에 대 한 두 개의 추가 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-108">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="2524c-109">명령 프롬프트에서 빌드하는 경우 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5* 에서 LINQ 관련 dll을 수동으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-109">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="2524c-110">LINQ to DataSet 기능을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="2524c-110">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="2524c-111">기존 프로젝트에서 LINQ to DataSet 기능을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-111">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="2524c-112">System.string, **system.web** 및 system.xml에 대 한 **참조를 추가** 합니다 **.**</span><span class="sxs-lookup"><span data-stu-id="2524c-112">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="2524c-113">**솔루션 탐색기** 에서 **참조** 노드를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-113">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="2524c-114">**참조 관리자** 대화 상자에서 System.string, **system.web** **및 system.xml** **을 선택 합니다..**</span><span class="sxs-lookup"><span data-stu-id="2524c-114">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="2524c-115">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-115">Select **OK**.</span></span>

1. <span data-ttu-id="2524c-116">**System.object** 및 system.string에 대해 [using](../../../csharp/language-reference/keywords/using-directive.md) 지시문을 추가 하거나 Visual Basic의 [Imports 문을](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 추가 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="2524c-116">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="2524c-117">필요에 `using` `Imports` 따라 데이터베이스에 연결 하는 방법에 따라 **system.web** 또는 **system.object** 에 대 한 지시문 (또는 문)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2524c-117">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="2524c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2524c-118">See also</span></span>

- [<span data-ttu-id="2524c-119">LINQ to DataSet 시작</span><span class="sxs-lookup"><span data-stu-id="2524c-119">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
