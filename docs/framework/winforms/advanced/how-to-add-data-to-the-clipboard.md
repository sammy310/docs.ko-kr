---
title: '방법: 클립보드에 데이터 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 1f04203cd5c006f778d09ddc3fef3cfa1be4666e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717128"
---
# <a name="how-to-add-data-to-the-clipboard"></a>방법: 클립보드에 데이터 추가
<xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제 클립보드 기능과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다. 많은 응용 프로그램 데이터에 대 한 임시 저장소로 클립보드를 사용 합니다. 예를 들어 워드 프로세서 잘라내기 및 붙여넣기 작업 중 클립보드를 사용합니다. 클립보드 다른 응용 프로그램에서 데이터를 전송할 때도 유용 합니다.  
  
 클립보드에 데이터를 추가 하면 해당 형식을 사용할 수 있으면 다른 응용 프로그램 데이터를 인식할 수 있도록 데이터 형식을 지정할 수 있습니다. 또한 데이터를 사용할 수 있도록 다른 응용 프로그램의 수를 늘리려면 다양 한 형식으로 클립보드에 데이터를 추가할 수 있습니다.  
  
 클립보드 형식은 해당 형식을 사용 하는 응용 프로그램 관련된 데이터를 검색할 수 있도록 형식을 식별 하는 문자열입니다. <xref:System.Windows.Forms.DataFormats> 클래스 사용에 대 한 미리 정의 된 형식 이름을 제공 합니다. 사용자 고유의 형식 이름을 사용 하거나 해당 형식으로 개체의 형식을 사용할 수도 있습니다.  
  
 하나 이상의 형식으로 클립보드에 데이터를 추가 하려면 사용 된 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드. 이 메서드에 개체를 전달할 수 있습니다 하지만 여러 형식에 데이터를 추가 하려면 먼저 추가 해야 데이터를 별도 개체로 여러 형식으로 작동 하도록 설계 되었습니다. 일반적으로 데이터를 추가 합니다는 <xref:System.Windows.Forms.DataObject>를 구현 하는 모든 형식을 사용할 수 있지만 <xref:System.Windows.Forms.IDataObject> 인터페이스입니다.  
  
 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], 기본 클립보드 작업을 쉽게 수행할 수 있도록 설계 된 새 메서드를 사용 하 여 데이터를 클립보드에 직접 추가할 수 있습니다. 텍스트와 같은 단일의 공통 형식으로 데이터를 사용 하 여 작업할 때 이러한 메서드를 사용 합니다.  
  
> [!NOTE]
>  모든 Windows 기반 응용 프로그램은 클립보드를 공유 합니다. 따라서 내용이 변경 될 수 있습니다 다른 응용 프로그램으로 전환 합니다.  
>   
>  <xref:System.Windows.Forms.Clipboard> 단일 스레드 아파트 (STA) 모드를 설정 하는 스레드의 클래스 에서만 사용할 수 있습니다. 이 클래스를 사용 하려면 프로그램 `Main` 표시 된 메서드가 <xref:System.STAThreadAttribute> 특성입니다.  
>   
>  개체를 클립보드에 배치할 수 있도록 serializable 이어야 합니다. 직렬화 가능 형식 확인을 표시 하는 <xref:System.SerializableAttribute> 특성입니다. 클립보드 메서드에 순차 불가능 한 개체를 전달 하는 경우 메서드가 예외를 throw 하지 않고 실패 합니다. serialization에 대한 자세한 내용은 <xref:System.Runtime.Serialization>을 참조하세요.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>단일의 공통 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 된 <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, 또는 <xref:System.Windows.Forms.Clipboard.SetText%2A> 메서드. 이러한 메서드는 에서만 사용할 수 있습니다 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>사용자 지정 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드를 사용자 지정 형식 이름입니다. 이 메서드는 에서만 사용할 수 있습니다 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     미리 정의 된 형식 이름을 사용 하 여 사용할 수도 있습니다는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드. 자세한 내용은 <xref:System.Windows.Forms.DataFormats>을 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>여러 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 된 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드와 전달을 <xref:System.Windows.Forms.DataObject> 데이터를 포함 하는. 버전에서 클립보드에 데이터를 추가 하려면이 메서드를 사용 해야 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>참고자료
- [끌어서 놓기 작업 및 클립보드 지원](drag-and-drop-operations-and-clipboard-support.md)
- [방법: 클립보드에서 데이터 검색](how-to-retrieve-data-from-the-clipboard.md)
