---
description: '자세히 알아보기: StrongNameGetBlob 함수'
title: StrongNameGetBlob 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 72f7ce50ce6170a23e5b24b68f911ff58bebe3bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736442"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="a090c-103">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="a090c-103">StrongNameGetBlob Function</span></span>

<span data-ttu-id="a090c-104">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-104">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="a090c-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-105">This function has been deprecated.</span></span> <span data-ttu-id="a090c-106">대신 [ICLRStrongName:: StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-106">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a090c-107">구문</span><span class="sxs-lookup"><span data-stu-id="a090c-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a090c-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a090c-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="a090c-109">진행 로드할 실행 파일의 올바른 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-109">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a090c-110">진행 실행 파일을 로드할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-110">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a090c-111">[in, out] 요청 된 최대 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="a090c-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a090c-112">반환 시의 실제 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="a090c-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a090c-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="a090c-113">Return Value</span></span>  

 <span data-ttu-id="a090c-114">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a090c-115">설명</span><span class="sxs-lookup"><span data-stu-id="a090c-115">Remarks</span></span>  

 <span data-ttu-id="a090c-116">`StrongNameGetBlob`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-116">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a090c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a090c-117">Requirements</span></span>  

 <span data-ttu-id="a090c-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a090c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a090c-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="a090c-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a090c-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a090c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a090c-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a090c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a090c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a090c-122">See also</span></span>

- [<span data-ttu-id="a090c-123">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="a090c-123">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="a090c-124">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="a090c-124">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="a090c-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a090c-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
