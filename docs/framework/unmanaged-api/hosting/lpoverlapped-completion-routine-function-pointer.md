---
description: '자세한 정보: 함수 포인터 LPOVERLAPPED_COMPLETION_ROUTINE'
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
ms.openlocfilehash: 6645e6a9746404a4ae355a22cf16e6d164c63bed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679838"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="c549e-103">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="c549e-103">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>

<span data-ttu-id="c549e-104">장치에 대해 겹치는 (즉, 비동기) i/o가 완료 되었을 때 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-104">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="c549e-105">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c549e-106">구문</span><span class="sxs-lookup"><span data-stu-id="c549e-106">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c549e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c549e-107">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="c549e-108">진행 장치를 닫은 경우의 오류 코드 값입니다. 그렇지 않으면이 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-108">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="c549e-109">장치를 닫으면 장치에 대 한 보류 중인 모든 i/o가 즉시 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-109">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="c549e-110">진행 I/o 작업에서 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-110">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="c549e-111">진행 I/o 요청을 완료 하는 데 사용할 정보가 들어 있는 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-111">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c549e-112">설명</span><span class="sxs-lookup"><span data-stu-id="c549e-112">Remarks</span></span>  

 <span data-ttu-id="c549e-113">`LPOVERLAPPED_COMPLETION_ROUTINE`요소가 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-113">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="c549e-114">콜백 함수를 사용 하면 호스트에서 완료 된 i/o 요청을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c549e-114">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c549e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c549e-115">Requirements</span></span>  

 <span data-ttu-id="c549e-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c549e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c549e-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c549e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c549e-118">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c549e-118">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c549e-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c549e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c549e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c549e-120">See also</span></span>

- [<span data-ttu-id="c549e-121">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c549e-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
