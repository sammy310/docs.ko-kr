---
title: 함수 활성화-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734504"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="de2a7-102">Activate 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="de2a7-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="de2a7-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="de2a7-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="de2a7-104">Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de2a7-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="de2a7-105">구문</span><span class="sxs-lookup"><span data-stu-id="de2a7-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="de2a7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de2a7-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="de2a7-107">창의 활성화 매개 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de2a7-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="de2a7-108"><xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 개체에 대 한 포인터를 포함 하는 단일 요소 버퍼의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de2a7-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="de2a7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de2a7-109">Requirements</span></span>

<span data-ttu-id="de2a7-110">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de2a7-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="de2a7-111">**GDIPLUS.DLL**</span><span class="sxs-lookup"><span data-stu-id="de2a7-111">**DLL:**</span></span>

<span data-ttu-id="de2a7-112">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="de2a7-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="de2a7-113">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="de2a7-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="de2a7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2a7-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="de2a7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de2a7-115">See also</span></span>

- [<span data-ttu-id="de2a7-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="de2a7-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
