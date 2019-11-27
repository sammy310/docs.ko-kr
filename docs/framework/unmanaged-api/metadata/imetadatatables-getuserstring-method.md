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
ms.openlocfilehash: 5936ca837c9ab452e992fcb09aacb476ab37316a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431426"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="af7d0-102">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="af7d0-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="af7d0-103">현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af7d0-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="af7d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="af7d0-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="af7d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af7d0-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="af7d0-106">진행 하드 코딩 된 문자열이 검색 되는 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af7d0-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="af7d0-107">제한이 `ppData`의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af7d0-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="af7d0-108">제한이 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af7d0-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="af7d0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af7d0-109">Requirements</span></span>

<span data-ttu-id="af7d0-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af7d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="af7d0-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="af7d0-111">**Header:** Cor.h</span></span>

<span data-ttu-id="af7d0-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af7d0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="af7d0-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af7d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="af7d0-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="af7d0-114">See also</span></span>

- [<span data-ttu-id="af7d0-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af7d0-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="af7d0-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af7d0-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
