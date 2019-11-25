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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>방법: 파일 대화 상자에 사용자 지정 위치 추가
Windows Vista의 기본 열기 및 저장 대화 상자는 대화 상자 왼쪽에 **즐겨찾기 링크**라는 영역을 포함 합니다. 이 영역을 사용자 지정 위치라고 합니다. <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 사용 하 여 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션에 폴더를 추가할 수 있습니다.  
  
> [!NOTE]
> 사용자 지정 위치가 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog>에 표시 되려면 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 `true` (기본값)로 설정 해야 합니다.  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>파일 대화 상자에 사용자 지정 위치를 추가하려면  
  
- 대화 상자의 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션에 경로, 알려진 폴더 GUID 또는 <xref:System.Windows.Forms.FileDialogCustomPlace> 개체를 추가 합니다.  
  
     다음 코드 예제에서는 경로를 추가하는 방법을 보여 줍니다.  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [파일 대화 상자의 사용자 지정 위치에 대한 알려진 폴더 GUID](known-folder-guids-for-file-dialog-custom-places.md)
