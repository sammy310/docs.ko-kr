---
title: 컨트롤의 다중 스레딩
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742136"
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows Forms 컨트롤의 다중 스레딩
많은 응용 프로그램에서 다른 스레드에서 시간이 많이 걸리는 작업을 수행 하 여 UI (사용자 인터페이스)의 응답성을 향상 시킬 수 있습니다. <xref:System.Threading> 네임 스페이스, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드 및 `BackgroundWorker` 구성 요소를 포함 하 여 Windows Forms 컨트롤의 다중 스레딩에 다양 한 도구를 사용할 수 있습니다.  
  
> [!NOTE]
> `BackgroundWorker` 구성 요소는 기능을 대체 하 고 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드를 추가 합니다. 그러나 이러한 기능은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다. 자세한 내용은 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)를 참조 하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Windows Forms 컨트롤을 스레드로부터 안전 하 게 호출 하는 방법을 보여 줍니다.  
  
 [방법: 백그라운드 스레드를 사용하여 파일 검색](how-to-use-a-background-thread-to-search-for-files.md)  
 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 사용 하 여 파일을 비동기적으로 검색 하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 비동기 작업에 대 한 작업자 스레드를 캡슐화 하는 구성 요소를 문서화 합니다.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 소리를 비동기적으로 로드 하는 방법을 설명 합니다.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 이미지를 비동기적으로 로드 하는 방법을 설명 합니다.  
  
## <a name="related-sections"></a>관련 섹션  
 [방법: 백그라운드에서 작업 실행](how-to-run-an-operation-in-the-background.md)  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용 하 여 시간이 오래 걸리는 작업을 수행 하는 방법을 보여 줍니다.  
  
 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)  
 비동기 작업에 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용 하는 방법을 설명 하는 항목을 제공 합니다.
