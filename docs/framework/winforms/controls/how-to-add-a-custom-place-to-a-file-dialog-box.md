---
title: '방법: 파일 대화 상자에 사용자 지정 위치 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976985"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="94479-102">방법: 파일 대화 상자에 사용자 지정 위치 추가</span><span class="sxs-lookup"><span data-stu-id="94479-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="94479-103">Windows Vista의 기본 열기 및 저장 대화 상자는 대화 상자 왼쪽에 **즐겨찾기 링크**라는 영역을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="94479-103">The default open and save dialog boxes on Windows Vista have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="94479-104">이 영역을 사용자 지정 위치라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94479-104">This area is called custom places.</span></span> <span data-ttu-id="94479-105"><xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 사용 하 여 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션에 폴더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94479-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94479-106">사용자 지정 위치가 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog>에 표시 되려면 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 `true` (기본값)로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94479-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="94479-107">파일 대화 상자에 사용자 지정 위치를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="94479-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="94479-108">대화 상자의 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션에 경로, 알려진 폴더 GUID 또는 <xref:System.Windows.Forms.FileDialogCustomPlace> 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="94479-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="94479-109">다음 코드 예제에서는 경로를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94479-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="94479-110">참조</span><span class="sxs-lookup"><span data-stu-id="94479-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="94479-111">파일 대화 상자의 사용자 지정 위치에 대한 알려진 폴더 GUID</span><span class="sxs-lookup"><span data-stu-id="94479-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
