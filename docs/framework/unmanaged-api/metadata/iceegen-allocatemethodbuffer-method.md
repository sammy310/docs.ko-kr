---
title: ICeeGen::AllocateMethodBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 38b9ea2ffab439f55f0a6d34d7f42c7669629168
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177918"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="7d009-102">ICeeGen::AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="7d009-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="7d009-103">메서드에 대해 지정된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d009-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="7d009-104">이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d009-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d009-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d009-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d009-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d009-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="7d009-107">【인】 만들 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="7d009-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="7d009-108">【아웃】 반환된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7d009-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="7d009-109">【아웃】 메서드의 상대적인 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7d009-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d009-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d009-110">Requirements</span></span>  
 <span data-ttu-id="7d009-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d009-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d009-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="7d009-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d009-113">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7d009-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d009-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d009-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d009-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d009-115">See also</span></span>

- [<span data-ttu-id="7d009-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d009-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
