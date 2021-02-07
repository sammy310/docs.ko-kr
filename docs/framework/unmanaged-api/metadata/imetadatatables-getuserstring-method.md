---
description: '자세히 알아보기: IMetaDataTables:: GetUserString 메서드'
title: IMetaDataTables::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 0909bfb2dbf4e6a34b746da7397a82845c2129c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687690"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="ddbdb-103">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="ddbdb-103">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="ddbdb-104">현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ddbdb-104">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="ddbdb-105">구문</span><span class="sxs-lookup"><span data-stu-id="ddbdb-105">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="ddbdb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ddbdb-106">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="ddbdb-107">진행 하드 코딩 된 문자열이 검색 되는 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ddbdb-107">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="ddbdb-108">제한이 의 크기에 대 한 포인터입니다 `ppData` .</span><span class="sxs-lookup"><span data-stu-id="ddbdb-108">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="ddbdb-109">제한이 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ddbdb-109">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="ddbdb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ddbdb-110">Requirements</span></span>

<span data-ttu-id="ddbdb-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddbdb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ddbdb-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ddbdb-112">**Header:** Cor.h</span></span>

<span data-ttu-id="ddbdb-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddbdb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ddbdb-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddbdb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ddbdb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddbdb-115">See also</span></span>

- [<span data-ttu-id="ddbdb-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ddbdb-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ddbdb-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ddbdb-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
