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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380e248c8c4e3407fff868cdd9a5c63b63e50c69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697515"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="8f24f-102">IAssemblyCacheItem::CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="8f24f-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="8f24f-103">지정한 이름 및 형식을 사용 하 여 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f24f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f24f-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="8f24f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f24f-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="8f24f-106">[in] 같은 값이 지원에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="8f24f-107">[in] 만들 스트림의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="8f24f-108">[in] 스트리밍할 수 파일의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="8f24f-109">[in] 같은 값이 지원에 정의 된 형식에 따른 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="8f24f-110">[out] 반환 된 주소에 대 한 포인터 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8f24f-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="8f24f-111">[in, 선택 사항] 참조 하는 스트림의 최대 크기 `ppIStream`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f24f-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f24f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f24f-112">Requirements</span></span>

<span data-ttu-id="8f24f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f24f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8f24f-114">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8f24f-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="8f24f-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f24f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8f24f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f24f-116">See also</span></span>

- [<span data-ttu-id="8f24f-117">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f24f-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)