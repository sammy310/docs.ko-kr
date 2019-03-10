---
title: '방법: 설치 된 디코더 나열'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: c40bb79dde4a9baf8b84f3cda5fdabc6e30ad0b5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717533"
---
# <a name="how-to-list-installed-decoders"></a>방법: 설치 된 디코더 나열
응용 프로그램 특정 이미지 파일 형식을 읽을 수 있는지 여부를 결정 하는 컴퓨터에서 사용할 이미지 디코더를 나열 하려는 경우. <xref:System.Drawing.Imaging.ImageCodecInfo> 클래스를 제공 합니다 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 정적 메서드는 이미지 디코더를 사용할 수를 확인할 수 있도록 합니다. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 배열을 반환 <xref:System.Drawing.Imaging.ImageCodecInfo> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 설치 된 디코더 목록 및 해당 속성 값을 출력합니다.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows Forms 애플리케이션  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>에서의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.   
  
## <a name="see-also"></a>참고자료
- [방법: 설치 된 인코더 나열](how-to-list-installed-encoders.md)
- [관리되는 GDI+에서 이미지 인코더 및 디코더 사용](using-image-encoders-and-decoders-in-managed-gdi.md)
