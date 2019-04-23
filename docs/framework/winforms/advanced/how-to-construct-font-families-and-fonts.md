---
title: '방법: 글꼴 패밀리 및 글꼴 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 0a9dcd00d4bc3e64ae4fc9a1d4884fac18521825
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181222"
---
# <a name="how-to-construct-font-families-and-fonts"></a>방법: 글꼴 패밀리 및 글꼴 만들기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 글꼴 서체 하지만 다양 한 스타일을 사용 하 여 글꼴 패밀리로 그룹화합니다. 예를 들어, 굴림 글꼴 패밀리에는 다음 글꼴을 포함 되어 있습니다.  
  
-   Arial 일반  
  
-   Arial 굵게  
  
-   Arial 기울임꼴  
  
-   Arial 굵은 기울임꼴  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 패밀리를 구성 하려면 네 가지 스타일을 사용 하 여: 일반, 굵게, 기울임꼴 및 굵은 기울임꼴 등입니다. 형용사와 같은 *범위를 좁힐* 하 고 *반올림* 스타일; 간주 되지 않습니다 이들은 제품군 이름 부분을 대신 합니다. 예를 들어, 굴림는 다음 멤버로 구성 된 글꼴 패밀리:  
  
-   Arial 좁은 일반  
  
-   굵게 아미  
  
-   Arial 좁은 기울임꼴  
  
-   Arial 좁은 굵은 기울임꼴  
  
 사용 하 여 텍스트를 그리려면 먼저 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 구성 해야를 <xref:System.Drawing.FontFamily> 개체 및 <xref:System.Drawing.Font> 개체입니다. <xref:System.Drawing.FontFamily> 개체 (예: Arial) 서체를 지정 하며 <xref:System.Drawing.Font> 개체 크기, 스타일 및 단위를 지정 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 일반 스타일 Arial 글꼴 크기를 16 픽셀을 생성합니다. 다음 코드에서는 첫 번째 인수에 전달 합니다 <xref:System.Drawing.Font.%23ctor%2A> 생성자를 <xref:System.Drawing.FontFamily> 개체입니다. 두 번째 인수는 네 번째 인수에 의해 식별 되는 단위로 측정 되는 글꼴 크기를 지정 합니다. 세 번째 인수는 스타일을 식별합니다.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> 멤버인 합니다 <xref:System.Drawing.GraphicsUnit> 열거형 및 <xref:System.Drawing.FontStyle.Regular> 멤버인는 <xref:System.Drawing.FontStyle> 열거형입니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [글꼴 및 텍스트 사용](using-fonts-and-text.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
