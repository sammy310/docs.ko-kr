---
description: '자세한 정보: BC42033: 잘못 된 체크섬 값, 16 진수가 아닌 숫자 또는 홀수의 16 진수'
title: 체크섬 값이 잘못되었습니다. 16진수가 아니거나 16진수 값이 홀수입니다.
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 8af1ca5e3f733278054300c2a79134817c56cf5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797109"
---
# <a name="bc42033-bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="dc6db-103">BC42033: 잘못 된 체크섬 값, 16 진수가 아니거나 16 진수 숫자가 홀수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-103">BC42033: Bad checksum value, non hex digits or odd number of hex digits</span></span>

<span data-ttu-id="dc6db-104">체크섬 값의 16진수가 잘못되었거나 자릿수가 홀수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-104">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>

 <span data-ttu-id="dc6db-105">ASP.NET은 Visual Basic 소스 파일(확장명 .vb)을 생성할 때 체크섬을 계산하여 `#externalchecksum`으로 식별되는 숨겨진 소스 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-105">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="dc6db-106">.vb 파일을 생성하는 사용자도 이 작업을 수행할 수 있지만 해당 프로세스는 내부용으로 유지하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-106">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>

 <span data-ttu-id="dc6db-107">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-107">By default, this message is a warning.</span></span> <span data-ttu-id="dc6db-108">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc6db-108">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="dc6db-109">**오류 ID:** BC42033</span><span class="sxs-lookup"><span data-stu-id="dc6db-109">**Error ID:** BC42033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="dc6db-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="dc6db-110">To correct this error</span></span>

1. <span data-ttu-id="dc6db-111">ASP.NET에서 Visual Basic 소스 파일을 생성하는 경우 프로젝트 빌드를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-111">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>

2. <span data-ttu-id="dc6db-112">빌드를 다시 시작한 후에도 이 경고가 계속 발생하면 ASP.NET을 다시 설치하고 빌드를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-112">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>

3. <span data-ttu-id="dc6db-113">그래도 경고가 계속 발생하거나 ASP.NET을 사용하고 있지 않으면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dc6db-113">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc6db-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc6db-114">See also</span></span>

- [<span data-ttu-id="dc6db-115">ASP.NET 개요</span><span class="sxs-lookup"><span data-stu-id="dc6db-115">ASP.NET Overview</span></span>](/aspnet/overview)
- [<span data-ttu-id="dc6db-116">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="dc6db-116">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
