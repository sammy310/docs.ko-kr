---
title: ICLRDataTarget::Request 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: e5d7a6b9826a734363d6beeb2e3fab8422964558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113349"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="abede-102">ICLRDataTarget::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="abede-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="abede-103">구현에 정의 된 대로 작업을 요청 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abede-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abede-104">구문</span><span class="sxs-lookup"><span data-stu-id="abede-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abede-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="abede-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="abede-106">진행 사용자 정의.</span><span class="sxs-lookup"><span data-stu-id="abede-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="abede-107">진행 들어오는 요청에 사용 되는 입력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="abede-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="abede-108">진행 요청을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="abede-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="abede-109">진행 응답에 사용 되는 출력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="abede-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="abede-110">제한이 응답을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="abede-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abede-111">주의</span><span class="sxs-lookup"><span data-stu-id="abede-111">Remarks</span></span>  
 <span data-ttu-id="abede-112">`Request` 메서드는 지정 되지 않은 사용자 지정 작업의 추가를 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="abede-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="abede-113">즉,이 메서드는 인터페이스 정의를 수정할 필요 없이 확장성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="abede-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="abede-114">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="abede-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abede-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="abede-115">Requirements</span></span>  
 <span data-ttu-id="abede-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abede-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abede-117">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="abede-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="abede-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abede-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abede-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abede-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abede-120">참조</span><span class="sxs-lookup"><span data-stu-id="abede-120">See also</span></span>

- [<span data-ttu-id="abede-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="abede-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
