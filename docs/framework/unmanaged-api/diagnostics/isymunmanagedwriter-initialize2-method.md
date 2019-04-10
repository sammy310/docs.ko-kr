---
title: ISymUnmanagedWriter::Initialize2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e645f79018d4ad41451faa07eba860e68b917539
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187020"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="0e63f-102">ISymUnmanagedWriter::Initialize2 메서드</span><span class="sxs-lookup"><span data-stu-id="0e63f-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="0e63f-103">이 작성기가 연결 될 하는 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="0e63f-104">또한이 메서드는 프로그램 데이터베이스 (PDB) 파일의 최종 위치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e63f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0e63f-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e63f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e63f-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="0e63f-107">[in] 메타 데이터 내보내기 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="0e63f-108">[in] 에 대 한 포인터를 `WCHAR` 는 디버깅 기호가 쓰여진 파일 이름이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="0e63f-109">파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="0e63f-110">[in] 기호 작성기에 대 한 기호를 내보내는 지정 하는 경우를 지정 <xref:System.Runtime.InteropServices.ComTypes.IStream> 에 지정 된 파일 대신는 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="0e63f-111">`pIStream` 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="0e63f-112">[in] `true` 전체를 다시 빌드해야 합니다;이 경우 `false` 는 증분 컴파일을 경우.</span><span class="sxs-lookup"><span data-stu-id="0e63f-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="0e63f-113">[in] 에 대 한 포인터를 `WCHAR` PDB 파일의 최종 위치에 경로 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e63f-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="0e63f-114">Return Value</span></span>  
 <span data-ttu-id="0e63f-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0e63f-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e63f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e63f-116">Requirements</span></span>  
 <span data-ttu-id="0e63f-117">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e63f-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e63f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e63f-118">See also</span></span>

- [<span data-ttu-id="0e63f-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e63f-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="0e63f-120">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="0e63f-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
