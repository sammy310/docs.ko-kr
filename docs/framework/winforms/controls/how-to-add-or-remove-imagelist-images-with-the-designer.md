---
title: '방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628724"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거

여러 가지 다른 방법으로 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가할 수 있습니다. <xref:System.Windows.Forms.ImageList>연결 된 스마트 태그를 사용 하 여 이미지를 매우 빠르게 추가 하거나 <xref:System.Windows.Forms.ImageList>에서 여러 다른 속성을 설정 하는 경우 속성 창 이미지를 추가 하는 것이 더 편리할 수 있습니다. 코드를 사용 하 여 이미지를 추가할 수도 있습니다. 코드를 사용 하 여 이미지를 추가 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms ImageList 구성 요소를 사용 하 여 이미지 추가 또는 제거](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조 하세요. 일반적으로는 컨트롤과 연결 되기 전에 <xref:System.Windows.Forms.ImageList> 구성 요소를 이미지로 채우지만이는 필요 하지 않습니다.

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>속성 창를 사용 하 여 이미지를 추가 하거나 제거 하려면

1. <xref:System.Windows.Forms.ImageList> 구성 요소를 선택 하거나 폼에 하나를 추가 합니다.

2. 속성 창에서 줄임표![(...) 단추를 클릭 하 여 <xref:System.Windows.Forms.ImageList.Images%2A> 속성 옆의 속성 창 Visual Studio.](./media/visual-studio-ellipsis-button.png))에서 줄임표 단추 (...)를 클릭 합니다.

3. **이미지 컬렉션 편집기**에서 **추가** 또는 **제거** 를 클릭 하 여 목록에서 이미지를 추가 하거나 제거 합니다.

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>스마트 태그를 사용 하 여 이미지를 추가 하거나 제거 하려면

1. <xref:System.Windows.Forms.ImageList> 구성 요소를 선택 하거나 폼에 하나를 추가 합니다.

2. 디자이너 작업 문자 모양을 클릭 합니다.![작은 검은색 화살표](./media/designer-actions-glyph.gif))

3. **ImageList 작업** 대화 상자에서 **이미지 선택**을 선택 합니다.

4. **이미지 컬렉션 편집기** 에서 **추가** 또는 **제거** 를 클릭 하 여 목록에서 이미지를 추가 하거나 제거 합니다.

## <a name="see-also"></a>참고 항목

- [이미지, 비트맵 및 메타파일](../advanced/images-bitmaps-and-metafiles.md)
- [연습: 디자이너 작업을 사용 하 여 일반 작업 수행](perform-common-tasks-design-actions.md)
- [ImageList 구성 요소](imagelist-component-windows-forms.md)
