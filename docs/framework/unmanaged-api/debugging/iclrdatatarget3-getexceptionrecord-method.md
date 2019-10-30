---
title: ICLRDataTarget3::GetExceptionRecord 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
ms.openlocfilehash: d5e7841844c8fa500935eb9cba06f4e2fe95d2d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111991"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="cdaf2-102">ICLRDataTarget3::GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="cdaf2-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="cdaf2-103">공용 언어 런타임(CLR)에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 예외 레코드 검색을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="cdaf2-104">예를 들어 덤프 대상의 경우이 값은 Windows 디버그 도움말 라이브러리 (Dbghelp.dll)의 [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) 함수에 `ExceptionParam` 인수를 통해 전달 된 예외 레코드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdaf2-105">구문</span><span class="sxs-lookup"><span data-stu-id="cdaf2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdaf2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdaf2-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="cdaf2-107">[in] 입력 버퍼 크기(바이트)로,</span><span class="sxs-lookup"><span data-stu-id="cdaf2-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="cdaf2-108">`sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="cdaf2-109">[out] 실제로 버퍼에 기록되는 바이트 수를 받는 `ULONG32` 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="cdaf2-110">[out] 예외 레코드 복사본을 받는 메모리 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="cdaf2-111">예외 레코드는 [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) 형식으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdaf2-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="cdaf2-112">Return Value</span></span>  
 <span data-ttu-id="cdaf2-113">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="cdaf2-114">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="cdaf2-115">반환 코드</span><span class="sxs-lookup"><span data-stu-id="cdaf2-115">Return code</span></span>|<span data-ttu-id="cdaf2-116">설명</span><span class="sxs-lookup"><span data-stu-id="cdaf2-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="cdaf2-117">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-117">Method succeeded.</span></span> <span data-ttu-id="cdaf2-118">예외 레코드가 출력 버퍼에 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="cdaf2-119">대상에 연결된 예외 레코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="cdaf2-120">입력 버퍼 크기가 `sizeof(MINIDUMP_EXCEPTION)`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdaf2-121">주의</span><span class="sxs-lookup"><span data-stu-id="cdaf2-121">Remarks</span></span>  
 <span data-ttu-id="cdaf2-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) 는 Windows SDK의 dbghelp.dll 및 데 필요한 imagehlp.dll에 정의 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="cdaf2-123">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdaf2-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdaf2-124">Requirements</span></span>  
 <span data-ttu-id="cdaf2-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdaf2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdaf2-126">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="cdaf2-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cdaf2-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdaf2-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdaf2-128">**.NET Framework 버전:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cdaf2-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdaf2-129">참조</span><span class="sxs-lookup"><span data-stu-id="cdaf2-129">See also</span></span>

- [<span data-ttu-id="cdaf2-130">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdaf2-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="cdaf2-131">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="cdaf2-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="cdaf2-132">GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="cdaf2-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
