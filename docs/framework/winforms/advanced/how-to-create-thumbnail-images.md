---
title: '방법: 썸네일 이미지 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 79b6258e7e6d7f16cc7a1e32a0c99dfe0eaeaa0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144016"
---
# <a name="how-to-create-thumbnail-images"></a>방법: 썸네일 이미지 만들기
축소판 그림 이미지를 이미지의 작은 버전이 있습니다. 호출 하 여 썸네일 이미지를 만들 수 있습니다 합니다 <xref:System.Drawing.Image.GetThumbnailImage%2A> 메서드는 <xref:System.Drawing.Image> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 된 <xref:System.Drawing.Image> JPG 파일에서 개체입니다. 원래 이미지 640 픽셀 너비, 높이 479 픽셀로 있습니다. 코드는 100 픽셀 너비와 높이가 100 픽셀의 축소판 그림 이미지를 만듭니다.  
  
 다음 그림에서는 미리 보기 이미지를 보여 줍니다.  
  
 ![축소판 그림 이미지](./media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  이 예제에서는 콜백 메서드를 선언 되었지만 사용 되지 않습니다. 이 GDI +의 모든 버전을 지원합니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 예제를 실행 하려면 다음이 단계를 수행 합니다.  
  
1.  새 Windows Forms 애플리케이션을 만듭니다.  
  
2.  예제 코드를 양식에 추가 합니다.  
  
3.  폼에 대 한 처리기를 만들고 <xref:System.Windows.Forms.Control.Paint> 이벤트  
  
4.  에 <xref:System.Windows.Forms.Control.Paint> 처리기를 호출 합니다 `GetThumbnail` 메서드와 전달 `e` 에 대 한 <xref:System.Windows.Forms.PaintEventArgs>합니다.  
  
5.  미리 보기를 확인 하려는 이미지 파일을 찾습니다.  
  
6.  에 `GetThumbnail` 메서드, 경로 지정 하 고 파일 이름 이미지입니다.  
  
7.  F5 키를 눌러 예제를 실행 합니다.  
  
     100 여 100 축소판 그림 이미지를 폼에 표시 됩니다.  
  
## <a name="see-also"></a>참고자료

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
