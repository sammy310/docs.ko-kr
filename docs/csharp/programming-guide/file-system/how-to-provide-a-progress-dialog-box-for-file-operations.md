---
title: 파일 작업에 대한 진행률 대화 상자를 제공하는 방법 - C# 프로그래밍 가이드
description: CopyFile(String, String, UIOption) 메서드를 사용하여 파일 작업에 대한 진행률 대화 상자를 제공하는 방법을 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 5d16aeb3a5394ca250e4a5e26074db797c54216d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185888"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="a34d7-103">파일 작업에 대한 진행률 대화 상자를 제공하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a34d7-103">How to provide a progress dialog box for file operations (C# Programming Guide)</span></span>

<span data-ttu-id="a34d7-104"><xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임스페이스의 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 메서드를 사용하는 경우 Windows에서 파일 작업 진행률을 보여 주는 표준 대화 상자를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-104">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="a34d7-105">Visual Studio에서 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a34d7-105">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="a34d7-106">메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-106">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="a34d7-107">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-107">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="a34d7-108">**어셈블리** 영역에서 **프레임워크**가 선택되지 않은 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-108">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="a34d7-109">이름 목록에서 **Microsoft.VisualBasic** 확인란을 선택한 다음 **확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-109">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a34d7-110">예제</span><span class="sxs-lookup"><span data-stu-id="a34d7-110">Example</span></span>  

 <span data-ttu-id="a34d7-111">다음 코드는 `sourcePath`로 지정된 디렉터리를 `destinationPath`로 지정된 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-111">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="a34d7-112">또한 이 코드는 작업이 완료되기까지 남은 예상 시간을 보여 주는 표준 대화 상자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a34d7-112">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="a34d7-113">참조</span><span class="sxs-lookup"><span data-stu-id="a34d7-113">See also</span></span>

- [<span data-ttu-id="a34d7-114">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a34d7-114">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
