---
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
ms.openlocfilehash: e99346ecca651346b46c220a5e427cbc7f4c4697
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095009"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="c530c-102">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="c530c-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="c530c-103">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="c530c-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-104">This function has been deprecated.</span></span> <span data-ttu-id="c530c-105">대신 [ICLRStrongName:: StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c530c-106">구문</span><span class="sxs-lookup"><span data-stu-id="c530c-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c530c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c530c-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c530c-108">진행 로드할 실행 파일의 올바른 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="c530c-109">진행 실행 파일을 로드할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="c530c-110">[in, out] `pbBlob`요청 된 최대 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="c530c-111">반환 시 `pbBlob`의 실제 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c530c-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="c530c-112">Return Value</span></span>  
 <span data-ttu-id="c530c-113">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c530c-114">주의</span><span class="sxs-lookup"><span data-stu-id="c530c-114">Remarks</span></span>  
 <span data-ttu-id="c530c-115">`StrongNameGetBlob` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c530c-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c530c-116">Requirements</span></span>  
 <span data-ttu-id="c530c-117">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c530c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c530c-118">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="c530c-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c530c-119">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c530c-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c530c-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c530c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c530c-121">참조</span><span class="sxs-lookup"><span data-stu-id="c530c-121">See also</span></span>

- [<span data-ttu-id="c530c-122">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="c530c-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="c530c-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="c530c-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="c530c-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c530c-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
