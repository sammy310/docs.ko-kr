---
description: '자세한 정보: 비동기 작업에서 오류 처리'
title: 비동기 작업에서 오류 처리
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: df223998737259aca01a4dc18ed9f2a911d80366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742409"
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="55bc9-103">비동기 작업에서 오류 처리</span><span class="sxs-lookup"><span data-stu-id="55bc9-103">Error handling in asynchronous activities</span></span>

<span data-ttu-id="55bc9-104"><xref:System.Activities.AsyncCodeActivity>에서 오류 처리를 제공하면 활동의 콜백 시스템을 통해 오류를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-104">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="55bc9-105">이 항목은 SendMail 활동 샘플을 사용하여 호스트에 비동기 작업에서 throw되는 오류가 발생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-105">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="55bc9-106">호스트에 비동기 활동에서 throw되는 오류 반환</span><span class="sxs-lookup"><span data-stu-id="55bc9-106">Returning an error thrown in an asynchronous activity back to the host</span></span>  

 <span data-ttu-id="55bc9-107">SendMail 활동 샘플에서 호스트에 비동기 작업의 오류를 라우팅하는 것은 다음 단계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-107">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
- <span data-ttu-id="55bc9-108">`SendMailAsyncResult` 클래스에 예외 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-108">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
- <span data-ttu-id="55bc9-109">`SendCompleted` 이벤트 처리기에서 해당 속성에 throw된 오류를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-109">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
- <span data-ttu-id="55bc9-110">`EndExecute` 이벤트 처리기에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-110">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="55bc9-111">결과 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55bc9-111">The resulting code is as follows.</span></span>  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;
        }  
    }  
```
