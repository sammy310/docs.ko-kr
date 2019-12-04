---
title: 사용자 지정 추적 레코드
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 986f0350c24414d0ff960474445adf6ac3f39734
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802624"
---
# <a name="custom-tracking-records"></a>사용자 지정 추적 레코드

이 항목에서는 사용자 지정 추적 레코드를 만들고 이 레코드와 함께 내보내질 데이터로 이 레코드를 채우는 방법을 보여 줍니다.

## <a name="emitting-custom-tracking-records"></a>사용자 지정 추적 레코드 내보내기

다음 예제에 표시된 것처럼 코드 활동에서 사용자 지정 추적 레코드를 내보낼 수 있습니다.

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<xref:System.Activities.Tracking.CustomTrackingRecord>에서 <xref:System.Activities.NativeActivityContext.Track%2A> 메서드를 호출하여 코드 활동에서 `ActivityContext`를 내보냅니다.

## <a name="see-also"></a>참조

- [Windows Server App Fabric 모니터링](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [App Fabric을 사용 하 여 응용 프로그램 모니터링](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
