---
title: 이중 버퍼링 사용
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777158"
---
# <a name="using-double-buffering"></a>이중 버퍼링 사용
복잡 한 그리기 작업을 포함 하는 응용 프로그램에서 깜빡임을 줄이기 위해 이중 버퍼링 된 그래픽을 사용할 수 있습니다. .NET Framework에는 이중 버퍼링에 대 한 기본 제공 지원이 포함 되어 있습니다. 또는 그래픽을 수동으로 렌더링 및 관리할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [이중 버퍼링 그래픽](double-buffered-graphics.md)  
 이중 버퍼링 개념을 간략하게 설명 하며.NET Framework 지원이 도입 되었습니다.  
  
 [방법: 폼 및 컨트롤에 이중 버퍼링 사용 하 여 그래픽 깜빡임 줄이기](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 기본 이중 지원.NET Framework의 버퍼링을 사용 하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링 된 그래픽 수동 관리](how-to-manually-manage-buffered-graphics.md)  
 응용 프로그램에서 이중 버퍼링을 관리 하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링 된 그래픽 수동 렌더링](how-to-manually-render-buffered-graphics.md)  
 이중 버퍼링 된 그래픽을 렌더링 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 이중 버퍼링을 사용 하도록 설정 하는 컨트롤의 메서드.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 그래픽 버퍼를 만드는 방법을 제공 합니다.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 응용 프로그램 도메인에 대 한 버퍼링 된 그래픽 컨텍스트에 대 한 액세스를 제공합니다.
