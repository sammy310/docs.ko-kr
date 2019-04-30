---
title: '방법: 클립보드에서 데이터 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: e8f77a4fd1047598d51c2e0932d9c1309a305a86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003927"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>방법: 클립보드에서 데이터 검색
<xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제 클립보드 기능과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다. 많은 응용 프로그램 데이터에 대 한 임시 저장소로 클립보드를 사용 합니다. 예를 들어 워드 프로세서 잘라내기 및 붙여넣기 작업 중 클립보드를 사용합니다. 클립보드 다른 응용 프로그램에서 정보를 전송할 때도 유용 합니다.  
  
 일부 응용 프로그램 데이터를 사용할 수 있도록 다른 응용 프로그램의 수를 늘리려면 여러 형식으로 클립보드에 데이터를 저장 합니다. 클립보드 형식은 형식을 식별 하는 문자열입니다. 식별 된 형식을 사용 하는 응용 프로그램은 클립보드에 연결 된 데이터를 검색할 수 있습니다. <xref:System.Windows.Forms.DataFormats> 클래스 사용에 대 한 미리 정의 된 형식 이름을 제공 합니다. 사용자 고유의 형식 이름을 사용 하거나 해당 형식으로 개체의 형식을 사용할 수도 있습니다. 클립보드에 데이터를 추가 하는 방법에 대 한 내용은 [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)합니다.  
  
 클립보드 데이터를 특정 형식으로 포함 되는지 여부를 확인 하려면 중 하나를 사용 합니다 `Contains` *형식을* 메서드 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드. 클립보드에서 데이터를 검색할 중 하나를 사용 합니다 `Get` *형식을* 메서드 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드. 이러한 메서드는의 새로운 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
 버전을 사용 하 여 클립보드의 데이터에 액세스 하려면 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]를 사용 합니다 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드 반환 된 메서드를 호출 <xref:System.Windows.Forms.IDataObject>. 특정 형식으로 반환된 된 개체의 사용 가능한 지 알아보려면, 예를 들어 호출 된 <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> 메서드.  
  
> [!NOTE]
>  모든 Windows 기반 응용 프로그램은 시스템 클립보드를 공유 합니다. 따라서 내용이 변경 될 수 있습니다 다른 응용 프로그램으로 전환 합니다.  
>   
>  <xref:System.Windows.Forms.Clipboard> 단일 스레드 아파트 (STA) 모드를 설정 하는 스레드의 클래스 에서만 사용할 수 있습니다. 이 클래스를 사용 하려면 프로그램 `Main` 표시 된 메서드가 <xref:System.STAThreadAttribute> 특성입니다.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>단일의 공통 형식으로 클립보드의 데이터를 검색 하려면  
  
1. 사용 된 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, 또는 <xref:System.Windows.Forms.Clipboard.GetText%2A> 메서드. 필요에 따라 해당를 사용할 `Contains` *형식* 방법 먼저 데이터를 특정 형식으로 사용할 수 있는지 여부를 결정 합니다. 이러한 메서드는 에서만 사용할 수 있습니다 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>사용자 지정 형식으로 클립보드의 데이터를 검색 하려면  
  
1. 사용 하 여는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드를 사용자 지정 형식 이름입니다. 이 메서드는 에서만 사용할 수 있습니다 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     미리 정의 된 형식 이름을 사용 하 여 사용할 수도 있습니다는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드. 자세한 내용은 <xref:System.Windows.Forms.DataFormats>을 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>여러 형식으로 클립보드의 데이터를 검색 하려면  
  
1. <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드를 사용하세요. 버전에서 클립보드의 데이터를 검색 하려면이 메서드를 사용 해야 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>참고자료

- [끌어서 놓기 작업 및 클립보드 지원](drag-and-drop-operations-and-clipboard-support.md)
- [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)
