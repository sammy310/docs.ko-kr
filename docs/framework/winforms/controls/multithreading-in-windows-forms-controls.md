---
title: Windows Forms 컨트롤의 다중 스레딩
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703324"
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows Forms 컨트롤의 다중 스레딩
많은 응용 프로그램에서 가능 사용자 인터페이스 (UI) 응답성 다른 스레드에서 시간이 많이 걸리는 작업을 수행 하 여 합니다. 다양 한 도구를 사용할 수 있습니다 다중 스레딩을 비롯 하 여 Windows Forms 컨트롤을 <xref:System.Threading> 네임 스페이스를 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드를 및 `BackgroundWorker` 구성 요소입니다.  
  
> [!NOTE]
>  그러나 합니다 `BackgroundWorker` 대체 하 고 기능을 추가 하는 구성 요소를 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드이 보존 이전 버전과 호환성 및 향후 사용을 위해 선택한 경우. 자세한 내용은 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 스레드로부터 안전한 Windows Forms 컨트롤 호출](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Windows Forms 컨트롤에 스레드로부터 안전한 호출을 수행 하는 방법을 보여 줍니다.  
  
 [방법: 파일을 검색 하는 백그라운드 스레드를 사용 합니다.](how-to-use-a-background-thread-to-search-for-files.md)  
 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 비동기적으로 파일을 검색 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 비동기 작업에 대 한 작업자 스레드를 캡슐화 하는 구성 요소를 설명 합니다.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 소리를 비동기적으로 로드 하는 방법을 설명 합니다.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 이미지를 비동기적으로 로드 하는 방법을 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [방법: 백그라운드에서 작업 실행](how-to-run-an-operation-in-the-background.md)  
 사용 하 여 시간이 오래 걸리는 작업을 수행 하는 방법을 보여 줍니다는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소입니다.  
  
 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)  
 사용 하는 방법을 설명 하는 항목을 제공 합니다 <xref:System.ComponentModel.BackgroundWorker> 비동기 작업에 대 한 구성 요소입니다.
