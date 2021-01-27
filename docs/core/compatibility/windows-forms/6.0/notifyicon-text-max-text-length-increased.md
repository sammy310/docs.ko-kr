---
title: '호환성이 손상되는 변경: NotifyIcon.Text 최대 텍스트 길이가 늘어남'
description: NotifyIcon.Text 속성의 최대 텍스트 길이가 늘어난 .NET 6.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 01/19/2021
ms.openlocfilehash: 0029556f3ec2795fb079575b329e7fbd187d486f
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98617980"
---
# <a name="notifyicontext-maximum-text-length-increased"></a><span data-ttu-id="e1f1d-103">NotifyIcon.Text 최대 텍스트 길이가 늘어남</span><span class="sxs-lookup"><span data-stu-id="e1f1d-103">NotifyIcon.Text maximum text length increased</span></span>

<span data-ttu-id="e1f1d-104"><xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> 속성에 허용되는 최대 텍스트 길이가 63자에서 127자로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-104">The maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property increased from 63 to 127.</span></span>

## <a name="change-description"></a><span data-ttu-id="e1f1d-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e1f1d-105">Change description</span></span>

<span data-ttu-id="e1f1d-106">이전 .NET 버전에서 <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> 속성에 허용되는 최대 텍스트 길이는 63자입니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-106">In previous .NET versions, the maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property is 63 characters.</span></span> <span data-ttu-id="e1f1d-107">.NET 6.0부터 허용되는 최대 텍스트 길이가 127자입니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-107">Starting in .NET 6.0, the maximum allowed text length is 127 characters.</span></span> <span data-ttu-id="e1f1d-108">모든 버전에서 제한보다 긴 값을 설정하려고 하면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-108">In any version, an <xref:System.ArgumentException> is thrown when you attempt to set a value that's longer than the limit.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="e1f1d-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e1f1d-109">Reason for change</span></span>

<span data-ttu-id="e1f1d-110">허용되는 최대 텍스트 길이가 [기본 Windows API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080)에 맞게 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-110">The maximum allowed text length was increased to be in line with the [underlying Windows API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080).</span></span> <span data-ttu-id="e1f1d-111">Windows API는 Windows 2000에서 업데이트되었지만, 호환성 때문에 .NET Framework에서 이 속성의 크기 제한이 업데이트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-111">The Windows API was updated in Windows 2000, but due to compatibility reasons, the size limit for this property wasn't updated in .NET Framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e1f1d-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e1f1d-112">Version introduced</span></span>

<span data-ttu-id="e1f1d-113">.NET 6.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="e1f1d-113">.NET 6.0 Preview 1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e1f1d-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e1f1d-114">Recommended action</span></span>

<span data-ttu-id="e1f1d-115">코드를 검토하고 필요한 경우 기존 가드 상태를 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f1d-115">Review your code and relax any existing guard conditions, if necessary.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e1f1d-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e1f1d-116">Affected APIs</span></span>

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->
