---
description: '자세한 정보: 로그 파일에 쓰기 때문에 MaximumSize 값을 초과 하 게 될 수 있으므로 로그 파일에 쓸 수 없습니다.'
title: MaximumSize 값을 초과할 수 있기 때문에 로그 파일에 쓸 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 5c305c550f7a63183a0ac529adc788fa79b5794f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456941"
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
  
## <a name="see-also"></a>추가 정보

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [내 응용 프로그램 .Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [DirectoryPath.](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
