---
title: 로그에 대한 스트림을 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 887356fac3abe5c9d28751f7c4d3b1908ed35acb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078387"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>로그에 대한 스트림을 가져올 수 없습니다.

로그에 대한 스트림을 가져올 수 없습니다. 을 기반으로 하는 잠재적인 파일 이름이 \<name> 이미 사용 중입니다.  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>기반으로 하는 모든 잠재적인 로그 파일 이름이 이미 사용 중 이므로 클래스에서 새 로그 파일을 만들 수 없습니다 \<name> .  
  
 로그 파일이 너무 많으면 애플리케이션의 아키텍처 문제를 나타낼 수도 있습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스에 대한 설명서를 참조하세요.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> 또는 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> 로 설정하여 로그 파일 이름에 날짜 스탬프를 포함합니다.  
  
2. <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [내 응용 프로그램 .Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [DirectoryPath.](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
