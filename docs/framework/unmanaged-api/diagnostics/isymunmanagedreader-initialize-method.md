---
title: ISymUnmanagedReader::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1986ed730c6f0a1ba8a2d8e3c688e6872184da9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736759"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="fa00c-102">ISymUnmanagedReader::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="fa00c-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="fa00c-103">이 판독기가 모듈의 파일 이름과 함께, 연결 되는 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa00c-104">이 메서드는 한 번만 호출할 수 있습니다 및 다른 판독기 메서드보다 먼저 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa00c-105">구문</span><span class="sxs-lookup"><span data-stu-id="fa00c-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa00c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa00c-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="fa00c-107">[in] 이 판독기가 연결 될 하는 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="fa00c-108">[in] 모듈의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-108">[in] The file name of the module.</span></span> <span data-ttu-id="fa00c-109">사용할 수는 `pIStream` 매개 변수 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="fa00c-110">[in] 검색할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-110">[in] The path to search.</span></span> <span data-ttu-id="fa00c-111">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="fa00c-112">[in] Filename 매개 변수에 대 안으로 사용 되는 파일 스트림.</span><span class="sxs-lookup"><span data-stu-id="fa00c-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa00c-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="fa00c-113">Return Value</span></span>  
 <span data-ttu-id="fa00c-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa00c-115">설명</span><span class="sxs-lookup"><span data-stu-id="fa00c-115">Remarks</span></span>  
 <span data-ttu-id="fa00c-116">중 하나만 지정 해야 합니다 `filename` 또는 `pIStream` 매개 변수를 둘 다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="fa00c-117">`searchPath` 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa00c-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa00c-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa00c-118">Requirements</span></span>  
 <span data-ttu-id="fa00c-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fa00c-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa00c-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa00c-120">See also</span></span>

- [<span data-ttu-id="fa00c-121">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa00c-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
