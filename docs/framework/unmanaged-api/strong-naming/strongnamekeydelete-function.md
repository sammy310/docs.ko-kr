---
title: StrongNameKeyDelete 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364517"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="59241-102">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="59241-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="59241-103">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="59241-103">Deletes the specified key container.</span></span>

<span data-ttu-id="59241-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59241-104">This function has been deprecated.</span></span> <span data-ttu-id="59241-105">사용 된 [iclrstrongname:: Strongnamekeydelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="59241-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="59241-106">구문</span><span class="sxs-lookup"><span data-stu-id="59241-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="59241-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59241-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="59241-108">[in] 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59241-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="59241-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="59241-109">Return Value</span></span>

<span data-ttu-id="59241-110">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="59241-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="59241-111">설명</span><span class="sxs-lookup"><span data-stu-id="59241-111">Remarks</span></span>

<span data-ttu-id="59241-112">사용 합니다 [StrongNameKeyInstall](strongnamekeyinstall-function.md) 컨테이너로 공개/개인 키 쌍을 가져오는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="59241-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="59241-113">경우는 `StrongNameKeyDelete` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="59241-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="59241-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59241-114">Requirements</span></span>

<span data-ttu-id="59241-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59241-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="59241-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="59241-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="59241-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="59241-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="59241-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59241-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="59241-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="59241-119">See also</span></span>

- [<span data-ttu-id="59241-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="59241-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="59241-121">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="59241-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="59241-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59241-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)