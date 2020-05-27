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
ms.openlocfilehash: 206dcd3a0a82da9b6211c8c2045e4e9d3d991973
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008874"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="349bf-102">ICeeGen::ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="349bf-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="349bf-103">지정 된 코드 섹션의 버퍼를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="349bf-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="349bf-105">구문</span><span class="sxs-lookup"><span data-stu-id="349bf-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="349bf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="349bf-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="349bf-107">진행 버퍼를 반환할 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="349bf-108">진행 포인터를 가져올 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="349bf-109">제한이 반환 된 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="349bf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="349bf-110">Requirements</span></span>  
 <span data-ttu-id="349bf-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="349bf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="349bf-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="349bf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="349bf-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="349bf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="349bf-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="349bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349bf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="349bf-115">See also</span></span>

- [<span data-ttu-id="349bf-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="349bf-116">ICeeGen Interface</span></span>](iceegen-interface.md)
