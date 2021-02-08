---
description: '자세히 알아보기: StrongNameKeyDelete 함수'
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
ms.openlocfilehash: 9314d961f79e673925125c2362308f9ab4533e75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781209"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="f72ec-103">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="f72ec-103">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="f72ec-104">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-104">Deletes the specified key container.</span></span>

<span data-ttu-id="f72ec-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-105">This function has been deprecated.</span></span> <span data-ttu-id="f72ec-106">대신 [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-106">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="f72ec-107">구문</span><span class="sxs-lookup"><span data-stu-id="f72ec-107">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="f72ec-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f72ec-108">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="f72ec-109">진행 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-109">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="f72ec-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="f72ec-110">Return Value</span></span>

<span data-ttu-id="f72ec-111">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-111">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f72ec-112">설명</span><span class="sxs-lookup"><span data-stu-id="f72ec-112">Remarks</span></span>

<span data-ttu-id="f72ec-113">[StrongNameKeyInstall](strongnamekeyinstall-function.md) 함수를 사용 하 여 공개/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-113">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="f72ec-114">`StrongNameKeyDelete`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-114">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="f72ec-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f72ec-115">Requirements</span></span>

<span data-ttu-id="f72ec-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f72ec-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f72ec-117">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="f72ec-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="f72ec-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f72ec-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="f72ec-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72ec-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f72ec-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f72ec-120">See also</span></span>

- [<span data-ttu-id="f72ec-121">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="f72ec-121">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f72ec-122">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="f72ec-122">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="f72ec-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f72ec-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
