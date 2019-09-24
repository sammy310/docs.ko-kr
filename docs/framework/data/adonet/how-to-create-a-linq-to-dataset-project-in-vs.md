---
title: Visual Studio에서 LINQ to DataSet 프로젝트 만들기
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783770"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="6c6a4-102">방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="6c6a4-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="6c6a4-103">LINQ 프로젝트의 다양한 형식에는 특정 어셈블리 참조 및 가져온 네임 스페이스 (Visual Basic)를 사용하거나 지시문 (C#)을 [사용](../../../csharp/language-reference/keywords/using-directive.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="6c6a4-104">LINQ의 최소 요구 사항은 *system.object* 에 대 한 참조 및 `using` 에 대 한 <xref:System.Linq>지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="6c6a4-105">이러한 요구 사항은 Visual Studio 2017에서 새 C# 콘솔 앱 프로젝트를 만드는 경우 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="6c6a4-106">이전 버전의 Visual Studio에서 프로젝트를 업그레이드 하는 경우 이러한 LINQ 관련 참조를 직접 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="6c6a4-107">LINQ to DataSet에는 *system.object* 및 *system.object*에 대 한 두 개의 추가 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="6c6a4-108">명령 프롬프트에서 빌드하는 경우 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*에서 LINQ 관련 dll을 수동으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="6c6a4-109">LINQ to DataSet 기능을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="6c6a4-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="6c6a4-110">기존 프로젝트에서 LINQ to DataSet 기능을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="6c6a4-111">System.string, **system.web**및 system.xml에 대 한 **참조를 추가**합니다 **.**</span><span class="sxs-lookup"><span data-stu-id="6c6a4-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="6c6a4-112">**솔루션 탐색기**에서 **참조** 노드를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="6c6a4-113">**참조 관리자** 대화 상자에서 System.string, **system.web** **및 system.xml** **을 선택 합니다..**</span><span class="sxs-lookup"><span data-stu-id="6c6a4-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="6c6a4-114">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-114">Select **OK**.</span></span>

1. <span data-ttu-id="6c6a4-115">**System.object** 및 system.string에 대해 [using](../../../csharp/language-reference/keywords/using-directive.md) 지시문을 추가 하거나 Visual Basic의 [Imports 문을](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 추가 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c6a4-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="6c6a4-116">필요에 따라 데이터베이스 `using` 에 연결 하 `Imports` 는 방법에 따라 **system.web** 또는 **system.object**에 대 한 지시문 (또는 문)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c6a4-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c6a4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c6a4-117">See also</span></span>

- [<span data-ttu-id="6c6a4-118">LINQ to DataSet 시작</span><span class="sxs-lookup"><span data-stu-id="6c6a4-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
