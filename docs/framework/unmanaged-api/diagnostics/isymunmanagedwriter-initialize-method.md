---
description: '자세히 알아보기: ISymUnmanagedWriter:: Initialize 메서드'
title: ISymUnmanagedWriter::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: eab60e9539df3d43a1602268d704ac324f028915
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762294"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="5ef32-103">ISymUnmanagedWriter::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="5ef32-103">ISymUnmanagedWriter::Initialize Method</span></span>

<span data-ttu-id="5ef32-104">이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-104">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="5ef32-105">이 메서드는 한 번만 호출할 수 있으며 다른 작성기 메서드 보다 먼저 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-105">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="5ef32-106">일부 작성기에는 파일 이름이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-106">Some writers may require a file name.</span></span> <span data-ttu-id="5ef32-107">그러나 파일 이름을 사용 하지 않는 작성기에는 부정적인 영향을 주지 않으면 서 항상이 메서드에 파일 이름을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-107">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef32-108">구문</span><span class="sxs-lookup"><span data-stu-id="5ef32-108">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef32-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ef32-109">Parameters</span></span>  

 `emitter`  
 <span data-ttu-id="5ef32-110">진행 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-110">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="5ef32-111">진행 디버깅 기호를 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-111">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="5ef32-112">파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-112">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="5ef32-113">진행 이 매개 변수를 지정 하면 기호 작성기가 <xref:System.Runtime.InteropServices.ComTypes.IStream> 매개 변수에 지정 된 파일 대신 지정 된에 기호를 내보냅니다 `filename` .</span><span class="sxs-lookup"><span data-stu-id="5ef32-113">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="5ef32-114">`pIStream` 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-114">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="5ef32-115">[in] `true` 전체 다시 작성 인 경우 `false` 증분 컴파일 인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-115">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef32-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="5ef32-116">Return Value</span></span>  

 <span data-ttu-id="5ef32-117">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef32-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef32-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ef32-118">Requirements</span></span>  

 <span data-ttu-id="5ef32-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5ef32-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef32-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ef32-120">See also</span></span>

- [<span data-ttu-id="5ef32-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ef32-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5ef32-122">Initialize2 메서드</span><span class="sxs-lookup"><span data-stu-id="5ef32-122">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)
