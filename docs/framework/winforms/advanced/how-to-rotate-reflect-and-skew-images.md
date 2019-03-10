---
title: '방법: 회전, 반사 및 기울이기 이미지'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 3e539f41667edb505269fe420396c79b68f34e8f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711501"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>방법: 회전, 반사 및 기울이기 이미지
회전, 반사 하 고 원본 이미지의 왼쪽 위, 오른쪽 위 및 왼쪽 아래 모퉁이 대 한 대상 점을 지정 하 여 이미지를 기울일 수 있습니다. 세 개의 대상 지점 원본 사각형이 이미지는 평행 사변형에 매핑되는 3x3 유사 변형을 결정 합니다.  
  
## <a name="example"></a>예제  
 예를 들어, 원본 이미지는 사각형의 왼쪽 위 모퉁이 사용 하 여 (0, 0), 오른쪽 위 모서리에서 (100, 0) 하 고 왼쪽 아래 모서리에서 (0, 50). 이제 이러한 매핑 한다고 가정 3 가리킵니다 대상 점을 다음과 같습니다.  
  
|원래 지점|대상 지점|  
|--------------------|-----------------------|  
|왼쪽 위 (0, 0)|(200, 20)|  
|오른쪽 위 (100, 0)|(110, 100)|  
|왼쪽 (0, 50)|(250, 30)|  
  
 다음 그림에서는 원본 이미지와 평행 사변형으로 매핑되는 이미지를 보여 줍니다. 원래 이미지 기울이기, 반영, 회전 되어 변환 합니다. 실행 하는 줄에 매핑된 원본 이미지의 위쪽 가장자리를 따라 x 축 (200, 20) 및 (110, 100). 원본 이미지의 왼쪽된 가장자리를 따라 y 축을 통해 실행 되는 줄에 매핑된 (200, 20) 및 (250, 30).  
  
 ![Stripes](./media/stripes1.gif "Stripes1")  
  
 다음 그림에서는 사진 이미지에 적용할 비슷한 변환을 보여 줍니다.  
  
 ![변환 오르기](./media/transformedclimber.png "TransformedClimber")  
  
 다음 그림은 메타 파일에 적용 된 비슷한 변환을 보여 줍니다.  
  
 ![메타 파일 변환](./media/transformedmetafile.png "TransformedMetafile")  
  
 다음 예제에서는 첫 번째 그림에 표시 된 이미지를 생성 합니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다. 바꿔야 `Stripes.bmp` 은 시스템에서 사용할 수 있는 이미지에 경로 사용 하 여 합니다.  
  
## <a name="see-also"></a>참고자료
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
