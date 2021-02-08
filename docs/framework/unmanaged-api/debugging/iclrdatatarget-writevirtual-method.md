---
description: '자세히 알아보기: ICLRDataTarget:: WriteVirtual 메서드'
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
ms.openlocfilehash: 29ff8d629c5797099dab155802fff99786f4ce15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794860"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="cec28-103">ICLRDataTarget::WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="cec28-103">ICLRDataTarget::WriteVirtual Method</span></span>

<span data-ttu-id="cec28-104">지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cec28-104">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec28-105">구문</span><span class="sxs-lookup"><span data-stu-id="cec28-105">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cec28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cec28-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="cec28-107">진행 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS입니다.</span><span class="sxs-lookup"><span data-stu-id="cec28-107">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="cec28-108">진행 쓸 데이터를 저장 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cec28-108">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="cec28-109">진행 쓸 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cec28-109">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="cec28-110">제한이 쓰여진 실제 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cec28-110">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec28-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cec28-111">Requirements</span></span>  

 <span data-ttu-id="cec28-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cec28-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cec28-113">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="cec28-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cec28-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cec28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cec28-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cec28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec28-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cec28-116">See also</span></span>

- [<span data-ttu-id="cec28-117">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cec28-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
