---
title: '방법: 디자이너를 사용하여 그림 로드'
description: Windows Forms PictureBox 컨트롤을 사용 하 여 디자인 타임에 폼에 그림을 로드 하 고 표시 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325597"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>방법: 디자이너를 사용하여 그림 로드(Windows Forms)

Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용 하면 속성을 유효한 그림으로 설정 하 여 디자인 타임에 폼에서 그림을 로드 하 고 표시할 수 있습니다 <xref:System.Windows.Forms.PictureBox.Image%2A> . 다음 표에서는 허용 되는 파일 형식을 보여 줍니다.

|유형|파일 이름 확장명|
|---|---|
|Bitmap|.bmp|
|아이콘|.ico|
|GIF|.gif|
|Emf|.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>디자인 타임에 그림을 표시 하려면

1. <xref:System.Windows.Forms.PictureBox>폼에 컨트롤을 그립니다.

2. **속성** 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택 하 고 줄임표 단추를 선택 하 여 **열기** 대화 상자를 표시 합니다.

3. 특정 파일 형식 (예: .gif 파일)을 찾고 있는 경우 **파일 형식** 상자에서 선택 합니다.

4. 표시 하려는 파일을 선택 합니다.

## <a name="to-clear-the-picture-at-design-time"></a>디자인 타임에 그림을 지우려면

1. **속성** 창에서 속성을 선택 <xref:System.Windows.Forms.PictureBox.Image%2A> 합니다. 이미지 개체 이름 왼쪽에 표시 되는 작은 축소판 이미지를 마우스 오른쪽 단추로 클릭 한 다음 **다시 설정**을 선택 합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.PictureBox>
- [PictureBox 컨트롤 개요](picturebox-control-overview-windows-forms.md)
- [방법: 런타임에 그림의 크기 또는 위치 수정](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [방법: 런타임에 그림 설정](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 컨트롤](picturebox-control-windows-forms.md)
