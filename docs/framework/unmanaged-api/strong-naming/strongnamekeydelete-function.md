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
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141591"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="b3739-102">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="b3739-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="b3739-103">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-103">Deletes the specified key container.</span></span>

<span data-ttu-id="b3739-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-104">This function has been deprecated.</span></span> <span data-ttu-id="b3739-105">대신 [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3739-106">구문</span><span class="sxs-lookup"><span data-stu-id="b3739-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="b3739-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3739-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="b3739-108">진행 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="b3739-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3739-109">Return Value</span></span>

<span data-ttu-id="b3739-110">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3739-111">주의</span><span class="sxs-lookup"><span data-stu-id="b3739-111">Remarks</span></span>

<span data-ttu-id="b3739-112">[StrongNameKeyInstall](strongnamekeyinstall-function.md) 함수를 사용 하 여 공개/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="b3739-113">`StrongNameKeyDelete` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3739-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3739-114">Requirements</span></span>

<span data-ttu-id="b3739-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3739-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b3739-116">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="b3739-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="b3739-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3739-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b3739-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3739-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b3739-119">참조</span><span class="sxs-lookup"><span data-stu-id="b3739-119">See also</span></span>

- [<span data-ttu-id="b3739-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="b3739-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="b3739-121">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="b3739-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="b3739-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3739-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
