---
title: IAssemblyCacheItem::CreateStream 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134480"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="508e3-102">IAssemblyCacheItem::CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="508e3-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="508e3-103">지정 된 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="508e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="508e3-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="508e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="508e3-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="508e3-106">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="508e3-107">진행 만들 스트림의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="508e3-108">진행 스트리밍할 파일의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="508e3-109">진행 Fusion에 정의 된 형식별 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="508e3-110">제한이 반환 된 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="508e3-111">[in, 선택 사항] `ppIStream`에서 참조 하는 스트림의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="508e3-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="508e3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="508e3-112">Requirements</span></span>

<span data-ttu-id="508e3-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508e3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="508e3-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="508e3-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="508e3-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508e3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="508e3-116">참조</span><span class="sxs-lookup"><span data-stu-id="508e3-116">See also</span></span>

- [<span data-ttu-id="508e3-117">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="508e3-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
