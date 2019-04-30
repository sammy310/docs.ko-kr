---
title: '방법: Windows Form 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 85fb12028687578b76e0f16061deb9b9a4de70e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003979"
---
# <a name="how-to-print-a-windows-form"></a>방법: Windows Form 인쇄
개발 프로세스의 일환으로, 일반적으로 하려는 Windows Form의 복사본을 인쇄 합니다. 다음 코드 예제를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 포함 하는 전체 코드 예제는 `Main` 메서드.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
- 프린터에 액세스할 수 있는 권한이 없습니다.  
  
- 설치 된 프린터가 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 이 코드 예제를 실행 하기 위해 사용할 프린터를 사용 하 여 컴퓨터를 액세스할 수 있는 권한이 있어야 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Drawing.Printing.PrintDocument>
- [방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.](how-to-render-images-with-gdi.md)
- [방법: Windows Forms의 그래픽 인쇄](how-to-print-graphics-in-windows-forms.md)
