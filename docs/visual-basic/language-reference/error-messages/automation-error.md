---
description: '자세히 알아보기: 자동화 오류'
title: 자동화 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: bf3e61bb9b8fec9a831d211b70abdca322c1fe06
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106607"
---
# <a name="automation-error"></a><span data-ttu-id="b4b9b-103">자동화 오류</span><span class="sxs-lookup"><span data-stu-id="b4b9b-103">Automation error</span></span>

<span data-ttu-id="b4b9b-104">메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b9b-104">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="b4b9b-105">이 오류는 개체를 만든 애플리케이션에서 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b9b-105">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b4b9b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b4b9b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b4b9b-107">`Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b9b-107">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="b4b9b-108">액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b9b-108">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b9b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4b9b-109">See also</span></span>

- [<span data-ttu-id="b4b9b-110">오류 유형</span><span class="sxs-lookup"><span data-stu-id="b4b9b-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="b4b9b-111">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="b4b9b-111">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
