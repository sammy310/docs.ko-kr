---
title: LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59565b28991f6d61ff2c6c77540eace92461aa89
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490175"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="42c98-102">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="42c98-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="42c98-103">Overlapped는 호스트에 알리는 함수를 가리키는 (즉, 비동기) 장치에는 I/O 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="42c98-104">.NET Framework 4에서이 함수 포인터에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c98-105">구문</span><span class="sxs-lookup"><span data-stu-id="42c98-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42c98-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42c98-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="42c98-107">[in] 장치; 닫힌 경우 오류 코드 값 그렇지 않은 경우이 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="42c98-108">장치를 닫으면 모든 보류 중인 장치에는 I/O 즉시 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="42c98-109">[in] I/O 작업에 의해 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="42c98-110">[in] I/O 요청을 완료 하는 데 사용할 정보가 포함 된 구조에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42c98-111">설명</span><span class="sxs-lookup"><span data-stu-id="42c98-111">Remarks</span></span>  
 <span data-ttu-id="42c98-112">함수는 `LPOVERLAPPED_COMPLETION_ROUTINE` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성기에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="42c98-113">콜백 함수에는 완료 된 I/O 요청을 처리 하는 데 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c98-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c98-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42c98-114">Requirements</span></span>  
 <span data-ttu-id="42c98-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42c98-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42c98-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42c98-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42c98-117">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="42c98-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="42c98-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c98-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="42c98-119">See also</span></span>

- [<span data-ttu-id="42c98-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="42c98-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
