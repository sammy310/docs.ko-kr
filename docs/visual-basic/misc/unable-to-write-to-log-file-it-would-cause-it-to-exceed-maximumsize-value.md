---
title: MaximumSize 값을 초과할 수 있기 때문에 로그 파일에 쓸 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 95a7b9036e7c1494cd44c250b0580bab5144417b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059459"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>MaximumSize 값을 초과할 수 있기 때문에 로그 파일에 쓸 수 없습니다.

<xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스가 다음 이유로 로그 파일에 쓸 수 없습니다.  
  
- 로그 파일 크기(바이트)가 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 속성의 값보다 큽니다.  
  
     —및—  
  
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성의 값이 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>이었습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.  
  
2. 더 큰 로그를 허용하도록 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 속성의 값을 변경합니다.  
  
3. 로그가 너무 큰 경우 경고 없이 메시지를 무시하도록 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 로 설정합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [내 응용 프로그램 .Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [DirectoryPath.](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
