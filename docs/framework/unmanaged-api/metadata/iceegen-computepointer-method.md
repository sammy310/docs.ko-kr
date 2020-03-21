---
title: ICeeGen::ComputePointer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176099"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="0919f-102">ICeeGen::ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="0919f-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="0919f-103">지정된 코드 섹션에 대한 버퍼를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0919f-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="0919f-104">이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0919f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0919f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0919f-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0919f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0919f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0919f-107">【인】 버퍼를 반환할 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0919f-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="0919f-108">【인】 포인터를 얻을 메서드의 상대적인 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0919f-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0919f-109">【아웃】 반환된 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0919f-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0919f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0919f-110">Requirements</span></span>  
 <span data-ttu-id="0919f-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0919f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0919f-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="0919f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0919f-113">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0919f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0919f-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0919f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0919f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0919f-115">See also</span></span>

- [<span data-ttu-id="0919f-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0919f-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
