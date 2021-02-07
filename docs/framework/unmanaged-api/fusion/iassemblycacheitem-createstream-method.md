---
description: '다음에 대 한 자세한 정보: IAssemblyCacheItem:: CreateStream 메서드'
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
ms.openlocfilehash: 89592d8fe1a7f43a7da20dd10883881c3339f088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760875"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="f5857-103">IAssemblyCacheItem::CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="f5857-103">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="f5857-104">지정 된 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-104">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5857-105">구문</span><span class="sxs-lookup"><span data-stu-id="f5857-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="f5857-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5857-106">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="f5857-107">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-107">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="f5857-108">진행 만들 스트림의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-108">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="f5857-109">진행 스트리밍할 파일의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-109">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="f5857-110">진행 Fusion에 정의 된 형식별 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-110">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="f5857-111">제한이 반환 된 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-111">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="f5857-112">[in, 선택 사항] 에서 참조 하는 스트림의 최대 크기 `ppIStream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f5857-112">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5857-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5857-113">Requirements</span></span>

<span data-ttu-id="f5857-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5857-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f5857-115">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f5857-115">**Header:** Fusion.h</span></span>

<span data-ttu-id="f5857-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5857-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f5857-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5857-117">See also</span></span>

- [<span data-ttu-id="f5857-118">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5857-118">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
