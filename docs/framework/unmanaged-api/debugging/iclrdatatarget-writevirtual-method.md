---
title: ICLRDataTarget::WriteVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: c6b4303163140c9c5553d02855c64dd2a3f5b134
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112744"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="eee05-102">ICLRDataTarget::WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="eee05-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="eee05-103">지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="eee05-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee05-104">구문</span><span class="sxs-lookup"><span data-stu-id="eee05-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eee05-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="eee05-106">진행 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS입니다.</span><span class="sxs-lookup"><span data-stu-id="eee05-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="eee05-107">진행 쓸 데이터를 저장 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eee05-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="eee05-108">진행 쓸 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eee05-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="eee05-109">제한이 쓰여진 실제 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eee05-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee05-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eee05-110">Requirements</span></span>  
 <span data-ttu-id="eee05-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eee05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee05-112">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="eee05-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="eee05-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eee05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eee05-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee05-115">참조</span><span class="sxs-lookup"><span data-stu-id="eee05-115">See also</span></span>

- [<span data-ttu-id="eee05-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eee05-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
