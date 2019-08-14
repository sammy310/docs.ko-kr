---
title: '방법: 디자이너를 사용 하 여 그림 로드 (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972366"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>방법: 디자이너를 사용 하 여 그림 로드 (Windows Forms)

Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용 하면 속성을 <xref:System.Windows.Forms.PictureBox.Image%2A> 유효한 그림으로 설정 하 여 디자인 타임에 폼에서 그림을 로드 하 고 표시할 수 있습니다. 다음 표에서는 허용 되는 파일 형식을 보여 줍니다.

|형식|파일 이름 확장명|
|----------|-------------------------|
|Bitmap|.bmp|
|아이콘|.ico|
|GIF|.gif|
|Emf|.wmf|
|JPEG|.jpg|

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.

## <a name="to-display-a-picture-at-design-time"></a>디자인 타임에 그림을 표시 하려면

1. 폼에 <xref:System.Windows.Forms.PictureBox> 컨트롤을 그립니다.

2. 속성 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택 하 고 줄임표 단추를 클릭 하 여 **열기** 대화 상자를 표시 합니다.

3. 특정 파일 형식 (예: .gif 파일)을 찾고 있는 경우 **파일 형식** 상자에서 선택 합니다.

4. 표시 하려는 파일을 선택 합니다.

## <a name="to-clear-the-picture-at-design-time"></a>디자인 타임에 그림을 지우려면

1. **속성** 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택 하 고 이미지 개체 이름 왼쪽에 표시 되는 작은 축소판 이미지를 마우스 오른쪽 단추로 클릭 합니다. **다시 설정**을 선택 합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.PictureBox>
- [PictureBox 컨트롤 개요](picturebox-control-overview-windows-forms.md)
- [방법: 런타임에 그림의 크기 또는 위치 수정](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [방법: 런타임에 그림 설정](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 컨트롤](picturebox-control-windows-forms.md)
