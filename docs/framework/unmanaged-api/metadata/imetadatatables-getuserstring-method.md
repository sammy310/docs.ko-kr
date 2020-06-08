---
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
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501146"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="9fe1b-102">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="9fe1b-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="9fe1b-103">현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9fe1b-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fe1b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fe1b-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="9fe1b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fe1b-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="9fe1b-106">진행 하드 코딩 된 문자열이 검색 되는 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9fe1b-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="9fe1b-107">제한이 의 크기에 대 한 포인터입니다 `ppData` .</span><span class="sxs-lookup"><span data-stu-id="9fe1b-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="9fe1b-108">제한이 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fe1b-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="9fe1b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fe1b-109">Requirements</span></span>

<span data-ttu-id="9fe1b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fe1b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9fe1b-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9fe1b-111">**Header:** Cor.h</span></span>

<span data-ttu-id="9fe1b-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fe1b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="9fe1b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9fe1b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fe1b-114">See also</span></span>

- [<span data-ttu-id="9fe1b-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe1b-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="9fe1b-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe1b-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
