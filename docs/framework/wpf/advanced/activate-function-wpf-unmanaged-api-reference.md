---
title: Activate 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777171"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c60d0-102">Activate 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c60d0-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="c60d0-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c60d0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="c60d0-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c60d0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="c60d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="c60d0-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="c60d0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c60d0-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="c60d0-107">활성화 매개 변수 창에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c60d0-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="c60d0-108">에 대 한 포인터를 포함 하는 단일 요소 버퍼의 주소에 대 한 포인터를 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c60d0-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="c60d0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c60d0-109">Requirements</span></span>

<span data-ttu-id="c60d0-110">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c60d0-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c60d0-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="c60d0-111">**DLL:**</span></span>

<span data-ttu-id="c60d0-112">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="c60d0-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="c60d0-113">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="c60d0-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="c60d0-114">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c60d0-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c60d0-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="c60d0-115">See also</span></span>

- [<span data-ttu-id="c60d0-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="c60d0-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
