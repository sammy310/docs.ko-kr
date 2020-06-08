---
title: '방법: 로그 메시지 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 28c5fe77e2711dfcac96e621a90fb9506eb74775
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410051"
---
# <a name="how-to-write-log-messages-visual-basic"></a>방법: 로그 메시지 쓰기(Visual Basic)

`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에 대한 정보를 기록할 수 있습니다. 이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록하는 방법을 보여 줍니다.

예외 정보를 기록하려면 `My.Application.Log.WriteException` 메서드를 사용합니다. [방법: 로그 예외](how-to-log-exceptions.md)를 참조하세요.

## <a name="example"></a>예제

이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록합니다.

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a>.NET Framework 보안

로그에 쓰는 데이터에 사용자 암호와 같은 중요한 정보가 포함되지 않도록 해야 합니다. 자세한 내용은 [애플리케이션 로그 작업](working-with-application-logs.md)을 참조하세요.

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [애플리케이션 로그 작업](working-with-application-logs.md)
- [방법: 로그 예외](how-to-log-exceptions.md)
- [연습: My.Application.Log가 정보를 기록하는 위치 확인](walkthrough-determining-where-my-application-log-writes-information.md)
- [연습: My.Application.Log가 정보를 기록하는 위치 변경](walkthrough-changing-where-my-application-log-writes-information.md)
- [연습: My.Application.Log 출력 필터링](walkthrough-filtering-my-application-log-output.md)
