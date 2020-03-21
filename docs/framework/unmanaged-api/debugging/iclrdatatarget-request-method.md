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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179109"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="752be-102">ICLRDataTarget::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="752be-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="752be-103">구현에 정의된 대로 작업을 요청하기 위해 공통 언어 런타임(CLR) 데이터 액세스 서비스에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="752be-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="752be-104">구문</span><span class="sxs-lookup"><span data-stu-id="752be-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="752be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="752be-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="752be-106">【인】 사용자 정의.</span><span class="sxs-lookup"><span data-stu-id="752be-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="752be-107">【인】 들어오는 요청에 사용되는 입력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="752be-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="752be-108">【인】 요청을 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="752be-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="752be-109">【인】 응답에 사용되는 출력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="752be-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="752be-110">【아웃】 응답을 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="752be-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="752be-111">설명</span><span class="sxs-lookup"><span data-stu-id="752be-111">Remarks</span></span>  
 <span data-ttu-id="752be-112">이 `Request` 메서드는 지정되지 않은 사용자 지정 작업을 쉽게 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="752be-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="752be-113">즉, 이 메서드는 인터페이스 정의의 수정없이 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="752be-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="752be-114">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="752be-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="752be-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="752be-115">Requirements</span></span>  
 <span data-ttu-id="752be-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="752be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="752be-117">**헤더:** 클러데이터.아이들, 클러데이터.h</span><span class="sxs-lookup"><span data-stu-id="752be-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="752be-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="752be-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="752be-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="752be-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752be-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="752be-120">See also</span></span>

- [<span data-ttu-id="752be-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="752be-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
