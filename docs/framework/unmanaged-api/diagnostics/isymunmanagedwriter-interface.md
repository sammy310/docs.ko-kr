---
title: ISymUnmanagedWriter 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: 8f0bbd26bde562df5482d167c9d2775e01426f55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610056"
---
# <a name="isymunmanagedwriter-interface"></a><span data-ttu-id="3ba50-102">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ba50-102">ISymUnmanagedWriter Interface</span></span>
<span data-ttu-id="3ba50-103">기호 작성기를 나타내며 문서, 시퀀스 위치, 어휘 범위 및 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ba50-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-104">Methods</span></span>  
  
|<span data-ttu-id="3ba50-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-105">Method</span></span>|<span data-ttu-id="3ba50-106">설명</span><span class="sxs-lookup"><span data-stu-id="3ba50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ba50-107">Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-107">Abort Method</span></span>](isymunmanagedwriter-abort-method.md)|<span data-ttu-id="3ba50-108">기호를 기호 저장소에 커밋하지 않고 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-108">Closes the symbol writer without committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="3ba50-109">Close 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-109">Close Method</span></span>](isymunmanagedwriter-close-method.md)|<span data-ttu-id="3ba50-110">기호를 기호 저장소에 커밋한 후 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-110">Closes the symbol writer after committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="3ba50-111">CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-111">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)|<span data-ttu-id="3ba50-112">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-112">Closes the current method.</span></span> <span data-ttu-id="3ba50-113">메서드를 닫은 후에는 더 이상 기호를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-113">Once a method is closed, no more symbols can be defined within it.</span></span>|  
|[<span data-ttu-id="3ba50-114">CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-114">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)|<span data-ttu-id="3ba50-115">가장 최근에 열린 네임 스페이스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-115">Closes the most recently opened namespace.</span></span>|  
|[<span data-ttu-id="3ba50-116">CloseScope 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-116">CloseScope Method</span></span>](isymunmanagedwriter-closescope-method.md)|<span data-ttu-id="3ba50-117">현재 어휘 범위를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-117">Closes the current lexical scope.</span></span>|  
|[<span data-ttu-id="3ba50-118">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-118">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)|<span data-ttu-id="3ba50-119">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-119">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="3ba50-120">DefineDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-120">DefineDocument Method</span></span>](isymunmanagedwriter-definedocument-method.md)|<span data-ttu-id="3ba50-121">소스 문서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-121">Defines a source document.</span></span>|  
|[<span data-ttu-id="3ba50-122">DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-122">DefineField Method</span></span>](isymunmanagedwriter-definefield-method.md)|<span data-ttu-id="3ba50-123">메서드 내에 없는 단일 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-123">Defines a single variable that is not within a method.</span></span>|  
|[<span data-ttu-id="3ba50-124">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-124">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)|<span data-ttu-id="3ba50-125">단일 전역 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-125">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="3ba50-126">DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-126">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)|<span data-ttu-id="3ba50-127">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-127">Defines a single variable in the current lexical scope.</span></span>|  
|[<span data-ttu-id="3ba50-128">DefineParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-128">DefineParameter Method</span></span>](isymunmanagedwriter-defineparameter-method.md)|<span data-ttu-id="3ba50-129">현재 메서드의 단일 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-129">Defines a single parameter in the current method.</span></span>|  
|[<span data-ttu-id="3ba50-130">DefineSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-130">DefineSequencePoints Method</span></span>](isymunmanagedwriter-definesequencepoints-method.md)|<span data-ttu-id="3ba50-131">현재 메서드 내에서 시퀀스 위치 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-131">Defines a group of sequence points within the current method.</span></span>|  
|[<span data-ttu-id="3ba50-132">GetDebugInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-132">GetDebugInfo Method</span></span>](isymunmanagedwriter-getdebuginfo-method.md)|<span data-ttu-id="3ba50-133">컴파일러가 PE (이식 가능한 실행) 파일 헤더에 디버그 디렉터리 항목을 쓰는 데 필요한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-133">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span>|  
|[<span data-ttu-id="3ba50-134">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-134">Initialize Method</span></span>](isymunmanagedwriter-initialize-method.md)|<span data-ttu-id="3ba50-135">이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-135">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>|  
|[<span data-ttu-id="3ba50-136">Initialize2 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-136">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)|<span data-ttu-id="3ba50-137">이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고, 디버깅 기호가 쓰여질 출력 파일 이름을 설정 하 고, PDB (프로그램 데이터베이스) 파일의 최종 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-137">Sets the metadata emitter interface with which this writer will be associated, sets the output file name to which the debugging symbols will be written, and sets the final location of the program database (PDB) file.</span></span>|  
|[<span data-ttu-id="3ba50-138">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-138">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)|<span data-ttu-id="3ba50-139">기호 정보를 내보내는 메서드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-139">Opens a method into which symbol information is emitted.</span></span>|  
|[<span data-ttu-id="3ba50-140">OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-140">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)|<span data-ttu-id="3ba50-141">새 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-141">Opens a new namespace.</span></span>|  
|[<span data-ttu-id="3ba50-142">OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-142">OpenScope Method</span></span>](isymunmanagedwriter-openscope-method.md)|<span data-ttu-id="3ba50-143">현재 메서드에서 새 어휘 범위를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-143">Opens a new lexical scope in the current method.</span></span>|  
|[<span data-ttu-id="3ba50-144">RemapToken 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-144">RemapToken Method</span></span>](isymunmanagedwriter-remaptoken-method.md)|<span data-ttu-id="3ba50-145">메타 데이터를 내보낼 때 메타 데이터 토큰이 다시 매핑되고 있음을 기호 작성기에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-145">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span>|  
|[<span data-ttu-id="3ba50-146">SetMethodSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-146">SetMethodSourceRange Method</span></span>](isymunmanagedwriter-setmethodsourcerange-method.md)|<span data-ttu-id="3ba50-147">소스 파일 내에서 메서드의 실제 시작과 끝을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-147">Specifies the true start and end of a method within a source file.</span></span>|  
|[<span data-ttu-id="3ba50-148">SetScopeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-148">SetScopeRange Method</span></span>](isymunmanagedwriter-setscoperange-method.md)|<span data-ttu-id="3ba50-149">지정된 어휘 범위에 대한 오프셋 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-149">Defines the offset range for the specified lexical scope.</span></span>|  
|[<span data-ttu-id="3ba50-150">SetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-150">SetSymAttribute Method</span></span>](isymunmanagedwriter-setsymattribute-method.md)|<span data-ttu-id="3ba50-151">이름에 따라 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-151">Defines a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="3ba50-152">SetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-152">SetUserEntryPoint Method</span></span>](isymunmanagedwriter-setuserentrypoint-method.md)|<span data-ttu-id="3ba50-153">이 모듈의 진입점인 사용자 정의 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-153">Specifies the user-defined method that is the entry point for this module.</span></span>|  
|[<span data-ttu-id="3ba50-154">UsingNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="3ba50-154">UsingNamespace Method</span></span>](isymunmanagedwriter-usingnamespace-method.md)|<span data-ttu-id="3ba50-155">지정 된 정규화 된 네임 스페이스 이름이 현재 열려 있는 어휘 범위 내에서 사용 되 고 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba50-155">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ba50-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3ba50-156">Requirements</span></span>  
 <span data-ttu-id="3ba50-157">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3ba50-157">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba50-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ba50-158">See also</span></span>

- [<span data-ttu-id="3ba50-159">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ba50-159">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3ba50-160">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ba50-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="3ba50-161">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ba50-161">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
