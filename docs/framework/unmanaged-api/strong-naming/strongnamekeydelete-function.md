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
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799025"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="d3db1-102">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="d3db1-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="d3db1-103">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-103">Deletes the specified key container.</span></span>

<span data-ttu-id="d3db1-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-104">This function has been deprecated.</span></span> <span data-ttu-id="d3db1-105">대신 [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3db1-106">구문</span><span class="sxs-lookup"><span data-stu-id="d3db1-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="d3db1-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3db1-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="d3db1-108">진행 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="d3db1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d3db1-109">Return Value</span></span>

<span data-ttu-id="d3db1-110">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3db1-111">설명</span><span class="sxs-lookup"><span data-stu-id="d3db1-111">Remarks</span></span>

<span data-ttu-id="d3db1-112">[StrongNameKeyInstall](strongnamekeyinstall-function.md) 함수를 사용 하 여 공개/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="d3db1-113">`StrongNameKeyDelete` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3db1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3db1-114">Requirements</span></span>

<span data-ttu-id="d3db1-115">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3db1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d3db1-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d3db1-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="d3db1-117">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3db1-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d3db1-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3db1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d3db1-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3db1-119">See also</span></span>

- [<span data-ttu-id="d3db1-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="d3db1-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="d3db1-121">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="d3db1-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="d3db1-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3db1-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
