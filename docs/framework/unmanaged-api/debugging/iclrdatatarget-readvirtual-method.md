---
title: ICLRDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: 0332fae46d6a65cfb7cc0b929cc2fd0d97e1790e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179151"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="dd943-102">ICLRDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="dd943-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="dd943-103">지정된 가상 메모리 주소의 데이터를 지정된 버퍼로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="dd943-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd943-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd943-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd943-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd943-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="dd943-106">【인】 가상 메모리 주소를 저장하는 CLRDATA_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="dd943-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="dd943-107">【아웃】 데이터를 받는 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dd943-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="dd943-108">【인】 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="dd943-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="dd943-109">【아웃】 반환된 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dd943-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd943-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd943-110">Requirements</span></span>  
 <span data-ttu-id="dd943-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd943-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd943-112">**헤더:** 클러데이터.아이들, 클러데이터.h</span><span class="sxs-lookup"><span data-stu-id="dd943-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dd943-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd943-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd943-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd943-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd943-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd943-115">See also</span></span>

- [<span data-ttu-id="dd943-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd943-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
