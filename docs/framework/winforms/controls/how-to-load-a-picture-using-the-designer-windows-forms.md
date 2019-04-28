---
title: '방법: (Windows Forms) 디자이너를 사용 하 여 그림 로드'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6bdf7c3df0ffd97dd88a4c442a8a73593a0447ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941065"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>방법: (Windows Forms) 디자이너를 사용 하 여 그림 로드
Windows Forms를 사용 하 여 <xref:System.Windows.Forms.PictureBox> 컨트롤을 로드 하 고 설정 하 여 디자인 타임에 폼에 그림을 표시 합니다 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 유효한 그림을 합니다. 다음 표에서 허용 되는 파일 형식을 보여 줍니다.  
  
|형식|파일 이름 확장명|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|아이콘|.ico|  
|GIF|.gif|  
|메타 파일|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-display-a-picture-at-design-time"></a>디자인 타임에 그림을 표시 하려면  
  
1. 그리기는 <xref:System.Windows.Forms.PictureBox> 폼의 컨트롤입니다.  
  
2. 속성 창에서 선택 합니다 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 표시 하려면 줄임표 단추를 클릭 합니다 **오픈** 대화 상자.  
  
3. 특정 파일 형식 (예를 들어,.gif 파일)을 찾으려는 경우에 선택 합니다 **파일 형식** 상자입니다.  
  
4. 표시 하려는 파일을 선택 합니다.  
  
### <a name="to-clear-the-picture-at-design-time"></a>디자인 타임에 그림을 삭제 하려면  
  
1. 에 **속성** 창에서를 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성과 이미지 개체의 이름 왼쪽에 표시 되는 작은 축소판 그림 이미지를 마우스 오른쪽 단추로 클릭 합니다. 선택할 **재설정**합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.PictureBox>
- [PictureBox 컨트롤 개요](picturebox-control-overview-windows-forms.md)
- [방법: 실행 시 크기 또는 그림의 위치 수정](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [방법: 런타임에 그림 설정](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 컨트롤](picturebox-control-windows-forms.md)
