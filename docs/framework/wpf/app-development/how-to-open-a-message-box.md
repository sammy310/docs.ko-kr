---
title: '방법: 메시지 상자 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123729"
---
# <a name="how-to-open-a-message-box"></a>방법: 메시지 상자 열기
이 예에서는 메시지 상자를 여는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 메시지 상자는 사용자에 게 정보를 표시 하기 위한 조립식 모달 대화 상자입니다. <xref:System.Windows.MessageBox> 클래스의 정적 <xref:System.Windows.MessageBox.Show%2A> 메서드를 호출 하 여 메시지 상자를 엽니다. <xref:System.Windows.MessageBox.Show%2A>를 호출 하면 메시지는 문자열 매개 변수를 사용 하 여 전달 됩니다. <xref:System.Windows.MessageBox.Show%2A>의 여러 오버 로드를 통해 메시지 상자가 표시 되는 방식을 구성할 수 있습니다 (<xref:System.Windows.MessageBox>참조).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>참고 항목

- [MessageBox 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
