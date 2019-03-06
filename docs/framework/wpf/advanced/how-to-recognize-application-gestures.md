---
title: '방법: 응용 프로그램 제스처 인식'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 99deaa528a089f2d16268747f2e946873f3420a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370516"
---
# <a name="how-to-recognize-application-gestures"></a>방법: 응용 프로그램 제스처 인식
다음 예제에서는 사용자 하면 잉크를 지우는 방법을 <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> 제스처는 <xref:System.Windows.Controls.InkCanvas>합니다. 이 예에서는 가정를 <xref:System.Windows.Controls.InkCanvas>라는 `inkCanvas1`, XAML 파일에서 선언 됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
