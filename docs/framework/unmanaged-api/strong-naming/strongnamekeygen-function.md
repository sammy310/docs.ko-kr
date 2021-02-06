---
description: '자세히 알아보기: StrongNameKeyGen 함수'
title: StrongNameKeyGen 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: c5f4cfcfa9030ae856acf5fd59ab34a2b8338670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636264"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="a1099-103">StrongNameKeyGen 함수</span><span class="sxs-lookup"><span data-stu-id="a1099-103">StrongNameKeyGen Function</span></span>

<span data-ttu-id="a1099-104">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-104">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="a1099-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-105">This function has been deprecated.</span></span> <span data-ttu-id="a1099-106">대신 [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-106">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1099-107">구문</span><span class="sxs-lookup"><span data-stu-id="a1099-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1099-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1099-108">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="a1099-109">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-109">[in] The requested key container name.</span></span> <span data-ttu-id="a1099-110">`wszKeyContainer` 임시 이름을 생성 하려면 비어 있지 않은 문자열 이거나 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-110">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a1099-111">진행 키를 등록 된 상태로 유지할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-111">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="a1099-112">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="a1099-113">0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하기 위해가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-113">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="a1099-114">0x00000001 ( `SN_LEAVE_KEY` )-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-114">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="a1099-115">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="a1099-116">제한이 의 크기 (바이트)입니다 `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="a1099-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1099-117">Return Value</span><span class="sxs-lookup"><span data-stu-id="a1099-117">Return Value</span></span>  

 <span data-ttu-id="a1099-118">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1099-119">설명</span><span class="sxs-lookup"><span data-stu-id="a1099-119">Remarks</span></span>  

 <span data-ttu-id="a1099-120">`StrongNameKeyGen`함수는 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-120">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="a1099-121">키를 검색 한 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="a1099-122">`StrongNameKeyGen`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-122">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1099-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1099-123">Requirements</span></span>  

 <span data-ttu-id="a1099-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1099-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1099-125">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="a1099-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a1099-126">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1099-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1099-127">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1099-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1099-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1099-128">See also</span></span>

- [<span data-ttu-id="a1099-129">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="a1099-129">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="a1099-130">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="a1099-130">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="a1099-131">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1099-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
