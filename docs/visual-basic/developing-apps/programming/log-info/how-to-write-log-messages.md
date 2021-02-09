---
description: '자세한 정보: 방법: 로그 메시지 쓰기(Visual Basic)'
title: '방법: 로그 메시지 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: ed455fdb2cebda908981514bef932942adf499ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797304"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="abbb2-103">방법: 로그 메시지 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abbb2-103">How to: Write Log Messages (Visual Basic)</span></span>

<span data-ttu-id="abbb2-104">`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb2-104">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="abbb2-105">이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abbb2-105">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>

<span data-ttu-id="abbb2-106">예외 정보를 기록하려면 `My.Application.Log.WriteException` 메서드를 사용합니다. [방법: 예외 기록](how-to-log-exceptions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abbb2-106">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

## <a name="example"></a><span data-ttu-id="abbb2-107">예제</span><span class="sxs-lookup"><span data-stu-id="abbb2-107">Example</span></span>

<span data-ttu-id="abbb2-108">이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb2-108">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a><span data-ttu-id="abbb2-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="abbb2-109">.NET Framework Security</span></span>

<span data-ttu-id="abbb2-110">로그에 쓰는 데이터에 사용자 암호와 같은 중요한 정보가 포함되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb2-110">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="abbb2-111">자세한 내용은 [애플리케이션 로그 작업](working-with-application-logs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abbb2-111">For more information, see [Working with Application Logs](working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="abbb2-112">참조</span><span class="sxs-lookup"><span data-stu-id="abbb2-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="abbb2-113">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="abbb2-113">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="abbb2-114">방법: 로그 예외</span><span class="sxs-lookup"><span data-stu-id="abbb2-114">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="abbb2-115">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="abbb2-115">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="abbb2-116">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="abbb2-116">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="abbb2-117">연습: My.Application.Log 출력 필터링</span><span class="sxs-lookup"><span data-stu-id="abbb2-117">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)
