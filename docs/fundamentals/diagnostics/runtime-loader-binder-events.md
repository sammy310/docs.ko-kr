---
title: 로더 및 바인더 런타임 이벤트
description: 어셈블리 로더 및 바인더에 대 한 정보를 수집 하는 로더 및 바인더 ETW 이벤트와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Assembly Loader events (CoreCLR)
- Assembly Binder events (CoreCLR)
- ETW, EventPipe, LTTng assembly loader and binder events (CoreCLR)
ms.openlocfilehash: 2284c580482f6b93a77f44649225ff7e5485666a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594111"
---
# <a name="net-runtime-loader-and-binder-events"></a><span data-ttu-id="b3e47-103">.NET 런타임 로더 및 바인더 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-103">.NET runtime loader and binder events</span></span>

<span data-ttu-id="b3e47-104">이러한 이벤트는 어셈블리 및 모듈 로드 및 언로드와 관련 된 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-104">These events collect information relating to loading and unloading assemblies and modules.</span></span> <span data-ttu-id="b3e47-105">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3e47-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

|<span data-ttu-id="b3e47-106">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-106">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-107">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-107">Event</span></span>|<span data-ttu-id="b3e47-108">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-108">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-109">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-109">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-110">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-110">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-111">Event</span></span>|<span data-ttu-id="b3e47-112">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-112">Event ID</span></span>|<span data-ttu-id="b3e47-113">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-113">Description</span></span>|
|-----------|--------------|-----------------|
|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-114">151</span><span class="sxs-lookup"><span data-stu-id="b3e47-114">151</span></span>|<span data-ttu-id="b3e47-115">애플리케이션 도메인에 대한 모듈이 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-115">Raised when a module is loaded for an application domain.</span></span>|

## <a name="moduleload_v2-event"></a><span data-ttu-id="b3e47-116">ModuleLoad_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-116">ModuleLoad_V2 event</span></span>

|<span data-ttu-id="b3e47-117">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-117">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-118">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-118">Event</span></span>|<span data-ttu-id="b3e47-119">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-119">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-120">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-120">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-121">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-121">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-122">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-122">Event</span></span>|<span data-ttu-id="b3e47-123">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-123">Event ID</span></span>|<span data-ttu-id="b3e47-124">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-124">Description</span></span>|
|-----------|--------------|-----------------|
|`ModuleLoad_V2`|<span data-ttu-id="b3e47-125">152</span><span class="sxs-lookup"><span data-stu-id="b3e47-125">152</span></span>|<span data-ttu-id="b3e47-126">프로세스 수명 중에 모듈이 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-126">Raised when a module is loaded during the lifetime of a process.</span></span>|

|<span data-ttu-id="b3e47-127">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-127">Field name</span></span>|<span data-ttu-id="b3e47-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-128">Data type</span></span>|<span data-ttu-id="b3e47-129">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-129">Description</span></span>|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="b3e47-130">모듈의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-130">Unique ID for the module.</span></span>|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-131">이 모듈이 있는 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-131">ID of the assembly in which this module resides.</span></span>|
|`ModuleFlags`|`win:UInt32`|<span data-ttu-id="b3e47-132">0x1: 도메인 중립 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-132">0x1: Domain neutral module.</span></span><br /><br /> <span data-ttu-id="b3e47-133">0x2: 모듈에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-133">0x2: Module has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-134">0x4: 동적 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-134">0x4: Dynamic module.</span></span><br /><br /> <span data-ttu-id="b3e47-135">0x8: 매니페스트 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-135">0x8: Manifest module.</span></span>|
|`Reserved1`|`win:UInt32`|<span data-ttu-id="b3e47-136">예약된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-136">Reserved field.</span></span>|
|`ModuleILPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-137">모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-137">Path of the Common Intermediate Language (CIL) image for the module, or dynamic module name if it is a dynamic assembly (null-terminated).</span></span>|
|`ModuleNativePath`|`win:UnicodeString`|<span data-ttu-id="b3e47-138">있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).</span><span class="sxs-lookup"><span data-stu-id="b3e47-138">Path of the module native image, if present (null-terminated).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-139">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-139">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|`ManagedPdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-140">이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-140">GUID signature of the managed program database (PDB) that matches this module.</span></span>|
|`ManagedPdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-141">이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-141">Age number written to the managed PDB that matches this module.</span></span>|
|`ManagedPdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-142">이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-142">Path to the location where the managed PDB that matches this module was built.</span></span> <span data-ttu-id="b3e47-143">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-143">In some cases, this may just be a file name.</span></span>|
|`NativePdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-144">이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-144">GUID signature of the Native Image Generator (NGen) PDB that matches this module, if applicable.</span></span>|
|`NativePdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-145">이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-145">Age number written to the NGen PDB that matches this module, if applicable.</span></span>|
|`NativePdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-146">이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-146">Path to the location where the NGen PDB that matches this module was built, if applicable.</span></span> <span data-ttu-id="b3e47-147">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-147">In some cases, this may just be a file name.</span></span>|

## <a name="moduleunload_v2-event"></a><span data-ttu-id="b3e47-148">ModuleUnload_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-148">ModuleUnload_V2 event</span></span>

|<span data-ttu-id="b3e47-149">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-149">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-150">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-150">Event</span></span>|<span data-ttu-id="b3e47-151">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-151">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-152">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-152">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-153">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-153">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-154">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-154">Event</span></span>|<span data-ttu-id="b3e47-155">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-155">Event ID</span></span>|<span data-ttu-id="b3e47-156">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-156">Description</span></span>|
|-----------|--------------|-----------------|
|`ModuleUnload_V2`|<span data-ttu-id="b3e47-157">153</span><span class="sxs-lookup"><span data-stu-id="b3e47-157">153</span></span>|<span data-ttu-id="b3e47-158">프로세스 수명 중에 모듈이 언로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-158">Raised when a module is unloaded during the lifetime of a process.</span></span>|

|<span data-ttu-id="b3e47-159">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-159">Field name</span></span>|<span data-ttu-id="b3e47-160">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-160">Data type</span></span>|<span data-ttu-id="b3e47-161">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-161">Description</span></span>|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="b3e47-162">모듈의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-162">Unique ID for the module.</span></span>|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-163">이 모듈이 있는 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-163">ID of the assembly in which this module resides.</span></span>|
|`ModuleFlags`|`win:UInt32`|<span data-ttu-id="b3e47-164">0x1: 도메인 중립 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-164">0x1: Domain neutral module.</span></span><br /><br /> <span data-ttu-id="b3e47-165">0x2: 모듈에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-165">0x2: Module has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-166">0x4: 동적 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-166">0x4: Dynamic module.</span></span><br /><br /> <span data-ttu-id="b3e47-167">0x8: 매니페스트 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-167">0x8: Manifest module.</span></span>|
|`Reserved1`|`win:UInt32`|<span data-ttu-id="b3e47-168">예약된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-168">Reserved field.</span></span>|
|`ModuleILPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-169">모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-169">Path of the Common Intermediate Language (CIL) image for the module, or dynamic module name if it is a dynamic assembly (null-terminated).</span></span>|
|`ModuleNativePath`|`win:UnicodeString`|<span data-ttu-id="b3e47-170">있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).</span><span class="sxs-lookup"><span data-stu-id="b3e47-170">Path of the module native image, if present (null-terminated).</span></span>|
|`ClrInstanceID`|``win:UInt16``|<span data-ttu-id="b3e47-171">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-171">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|`ManagedPdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-172">이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-172">GUID signature of the managed program database (PDB) that matches this module.</span></span>|
|`ManagedPdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-173">이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-173">Age number written to the managed PDB that matches this module.</span></span>|
|`ManagedPdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-174">이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-174">Path to the location where the managed PDB that matches this module was built.</span></span> <span data-ttu-id="b3e47-175">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-175">In some cases, this may just be a file name.</span></span>|
|`NativePdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-176">이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-176">GUID signature of the Native Image Generator (NGen) PDB that matches this module, if applicable.</span></span>|
|`NativePdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-177">이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-177">Age number written to the NGen PDB that matches this module, if applicable.</span></span>|
|`NativePdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-178">이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-178">Path to the location where the NGen PDB that matches this module was built, if applicable.</span></span> <span data-ttu-id="b3e47-179">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-179">In some cases, this may just be a file name.</span></span>|

## <a name="moduledcstart_v2-event"></a><span data-ttu-id="b3e47-180">ModuleDCStart_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-180">ModuleDCStart_V2 event</span></span>

|<span data-ttu-id="b3e47-181">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-181">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-182">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-182">Event</span></span>|<span data-ttu-id="b3e47-183">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-183">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-184">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-184">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-185">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-185">Informational (4)</span></span>

|<span data-ttu-id="b3e47-186">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-186">Event</span></span>|<span data-ttu-id="b3e47-187">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-187">Event ID</span></span>|<span data-ttu-id="b3e47-188">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-188">Description</span></span>
|-----------|--------------|-----------------|
|`ModuleDCStart_V2`|<span data-ttu-id="b3e47-189">153</span><span class="sxs-lookup"><span data-stu-id="b3e47-189">153</span></span>|<span data-ttu-id="b3e47-190">시작 런다운 중에 모듈을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-190">Enumerates modules during a start rundown.</span></span>|

|<span data-ttu-id="b3e47-191">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-191">Field name</span></span>|<span data-ttu-id="b3e47-192">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-192">Data type</span></span>|<span data-ttu-id="b3e47-193">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-193">Description</span></span>|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="b3e47-194">모듈의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-194">Unique ID for the module.</span></span>|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-195">이 모듈이 있는 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-195">ID of the assembly in which this module resides.</span></span>|
|`ModuleFlags`|`win:UInt32`|<span data-ttu-id="b3e47-196">0x1: 도메인 중립 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-196">0x1: Domain neutral module.</span></span><br /><br /> <span data-ttu-id="b3e47-197">0x2: 모듈에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-197">0x2: Module has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-198">0x4: 동적 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-198">0x4: Dynamic module.</span></span><br /><br /> <span data-ttu-id="b3e47-199">0x8: 매니페스트 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-199">0x8: Manifest module.</span></span>|
|`Reserved1`|`win:UInt32`|<span data-ttu-id="b3e47-200">예약된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-200">Reserved field.</span></span>|
|`ModuleILPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-201">모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-201">Path of the Common Intermediate Language (CIL) image for the module, or dynamic module name if it is a dynamic assembly (null-terminated).</span></span>|
|`ModuleNativePath`|`win:UnicodeString`|<span data-ttu-id="b3e47-202">있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).</span><span class="sxs-lookup"><span data-stu-id="b3e47-202">Path of the module native image, if present (null-terminated).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-203">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|`ManagedPdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-204">이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-204">GUID signature of the managed program database (PDB) that matches this module.</span></span>|
|`ManagedPdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-205">이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-205">Age number written to the managed PDB that matches this module.</span></span>|
|`ManagedPdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-206">이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-206">Path to the location where the managed PDB that matches this module was built.</span></span> <span data-ttu-id="b3e47-207">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-207">In some cases, this may just be a file name.</span></span>|
|`NativePdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-208">이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-208">GUID signature of the Native Image Generator (NGen) PDB that matches this module, if applicable.</span></span>|
|`NativePdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-209">이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-209">Age number written to the NGen PDB that matches this module, if applicable.</span></span>|
|`NativePdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-210">이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-210">Path to the location where the NGen PDB that matches this module was built, if applicable.</span></span> <span data-ttu-id="b3e47-211">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-211">In some cases, this may just be a file name.</span></span>|

## <a name="moduledcend_v2-event"></a><span data-ttu-id="b3e47-212">ModuleDCEnd_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-212">ModuleDCEnd_V2 event</span></span>

|<span data-ttu-id="b3e47-213">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-213">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-214">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-214">Event</span></span>|<span data-ttu-id="b3e47-215">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-215">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-216">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-216">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-217">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-217">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-218">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-218">Event</span></span>|<span data-ttu-id="b3e47-219">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-219">Event ID</span></span>|<span data-ttu-id="b3e47-220">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-220">Description</span></span>|
|-----------|--------------|-----------------|
|`ModuleDCEnd_V2`|<span data-ttu-id="b3e47-221">154</span><span class="sxs-lookup"><span data-stu-id="b3e47-221">154</span></span>|<span data-ttu-id="b3e47-222">끝 런다운 중에 모듈을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-222">Enumerates modules during an end rundown.</span></span>|

|<span data-ttu-id="b3e47-223">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-223">Field name</span></span>|<span data-ttu-id="b3e47-224">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-224">Data type</span></span>|<span data-ttu-id="b3e47-225">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-225">Description</span></span>|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="b3e47-226">모듈의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-226">Unique ID for the module.</span></span>|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-227">이 모듈이 있는 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-227">ID of the assembly in which this module resides.</span></span>|
|`ModuleFlags`|`win:UInt32`|<span data-ttu-id="b3e47-228">0x1: 도메인 중립 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-228">0x1: Domain neutral module.</span></span><br /><br /> <span data-ttu-id="b3e47-229">0x2: 모듈에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-229">0x2: Module has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-230">0x4: 동적 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-230">0x4: Dynamic module.</span></span><br /><br /> <span data-ttu-id="b3e47-231">0x8: 매니페스트 모듈.</span><span class="sxs-lookup"><span data-stu-id="b3e47-231">0x8: Manifest module.</span></span>|
|`Reserved1`|`win:UInt32`|<span data-ttu-id="b3e47-232">예약된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-232">Reserved field.</span></span>|
|`ModuleILPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-233">모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-233">Path of the Common Intermediate Language (CIL) image for the module, or dynamic module name if it is a dynamic assembly (null-terminated).</span></span>|
|`ModuleNativePath`|`win:UnicodeString`|<span data-ttu-id="b3e47-234">있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).</span><span class="sxs-lookup"><span data-stu-id="b3e47-234">Path of the module native image, if present (null-terminated).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-235">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|`ManagedPdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-236">이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-236">GUID signature of the managed program database (PDB) that matches this module.</span></span>|
|`ManagedPdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-237">이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-237">Age number written to the managed PDB that matches this module.</span></span>|
|`ManagedPdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-238">이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-238">Path to the location where the managed PDB that matches this module was built.</span></span> <span data-ttu-id="b3e47-239">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-239">In some cases, this may just be a file name.</span></span>|
|`NativePdbSignature`|`win:GUID`|<span data-ttu-id="b3e47-240">이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-240">GUID signature of the Native Image Generator (NGen) PDB that matches this module, if applicable.</span></span>|
|`NativePdbAge`|`win:UInt32`|<span data-ttu-id="b3e47-241">이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-241">Age number written to the NGen PDB that matches this module, if applicable.</span></span>|
|`NativePdbBuildPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-242">이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="b3e47-242">Path to the location where the NGen PDB that matches this module was built, if applicable.</span></span> <span data-ttu-id="b3e47-243">경우에 따라 파일 이름일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-243">In some cases, this may just be a file name.</span></span>|

## <a name="assemblyload_v1-event"></a><span data-ttu-id="b3e47-244">AssemblyLoad_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-244">AssemblyLoad_V1 event</span></span>

|<span data-ttu-id="b3e47-245">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-245">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-246">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-246">Event</span></span>|<span data-ttu-id="b3e47-247">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-247">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-248">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-248">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-249">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-249">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-250">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-250">Event</span></span>|<span data-ttu-id="b3e47-251">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-251">Event ID</span></span>|<span data-ttu-id="b3e47-252">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-252">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyLoad_V1`|<span data-ttu-id="b3e47-253">154</span><span class="sxs-lookup"><span data-stu-id="b3e47-253">154</span></span>|<span data-ttu-id="b3e47-254">어셈블리가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-254">Raised when an assembly is loaded.</span></span>|

|<span data-ttu-id="b3e47-255">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-255">Field name</span></span>|<span data-ttu-id="b3e47-256">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-256">Data type</span></span>|<span data-ttu-id="b3e47-257">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-257">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-258">어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-258">Unique ID for the assembly.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="b3e47-259">이 어셈블리의 도메인 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-259">ID of the domain of this assembly.</span></span>|
|`BindingID`|`win:UInt64`|<span data-ttu-id="b3e47-260">어셈블리 바인딩을 고유하게 식별하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-260">ID that uniquely identifies the assembly binding.</span></span>|
|`AssemblyFlags`|`win:UInt32`|<span data-ttu-id="b3e47-261">0x1: 도메인 중립 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-261">0x1: Domain neutral assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-262">0x2: 동적 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-262">0x2: Dynamic assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-263">0x4: 어셈블리에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-263">0x4: Assembly has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-264">0x8: 수집 가능한 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-264">0x8: Collectible assembly.</span></span>|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-265">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-265">Fully qualified assembly name.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-266">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-266">Unique ID for the instance of CoreCLR.</span></span>

## <a name="assemblyunload_v1-event"></a><span data-ttu-id="b3e47-267">AssemblyUnload_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-267">AssemblyUnload_V1 event</span></span>

|<span data-ttu-id="b3e47-268">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-268">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-269">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-269">Event</span></span>|<span data-ttu-id="b3e47-270">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-270">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-271">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-271">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-272">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-272">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-273">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-273">Event</span></span>|<span data-ttu-id="b3e47-274">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-274">Event ID</span></span>|<span data-ttu-id="b3e47-275">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-275">Description</span></span>|
|-----------|--------------|-----------------|
|`FireAssemblyUnload_V1`|<span data-ttu-id="b3e47-276">155</span><span class="sxs-lookup"><span data-stu-id="b3e47-276">155</span></span>|<span data-ttu-id="b3e47-277">어셈블리가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-277">Raised when an assembly is loaded.</span></span>|

|<span data-ttu-id="b3e47-278">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-278">Field name</span></span>|<span data-ttu-id="b3e47-279">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-279">Data type</span></span>|<span data-ttu-id="b3e47-280">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-280">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-281">어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-281">Unique ID for the assembly.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="b3e47-282">이 어셈블리의 도메인 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-282">ID of the domain of this assembly.</span></span>|
|`BindingID`|`win:UInt64`|<span data-ttu-id="b3e47-283">어셈블리 바인딩을 고유하게 식별하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-283">ID that uniquely identifies the assembly binding.</span></span>|
|`AssemblyFlags`|`win:UInt32`|<span data-ttu-id="b3e47-284">0x1: 도메인 중립 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-284">0x1: Domain neutral assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-285">0x2: 동적 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-285">0x2: Dynamic assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-286">0x4: 어셈블리에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-286">0x4: Assembly has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-287">0x8: 수집 가능한 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-287">0x8: Collectible assembly.</span></span>|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-288">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-288">Fully qualified assembly name.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-289">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-289">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="assemblydcstart_v1-event"></a><span data-ttu-id="b3e47-290">AssemblyDCStart_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-290">AssemblyDCStart_V1 event</span></span>

|<span data-ttu-id="b3e47-291">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-291">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-292">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-292">Event</span></span>|<span data-ttu-id="b3e47-293">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-293">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-294">`LoaderKeyword` (0x8)</span><span class="sxs-lookup"><span data-stu-id="b3e47-294">`LoaderKeyword` (0x8)</span></span>|`DomainModuleLoad_V1`|<span data-ttu-id="b3e47-295">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-295">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-296">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-296">Event</span></span>|<span data-ttu-id="b3e47-297">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-297">Event ID</span></span>|<span data-ttu-id="b3e47-298">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-298">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyDCStart_V1`|<span data-ttu-id="b3e47-299">155</span><span class="sxs-lookup"><span data-stu-id="b3e47-299">155</span></span>|<span data-ttu-id="b3e47-300">시작 런다운 중에 어셈블리를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-300">Enumerates assemblies during a start rundown.</span></span>|

|<span data-ttu-id="b3e47-301">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-301">Field name</span></span>|<span data-ttu-id="b3e47-302">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-302">Data type</span></span>|<span data-ttu-id="b3e47-303">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-303">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|<span data-ttu-id="b3e47-304">어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-304">Unique ID for the assembly.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="b3e47-305">이 어셈블리의 도메인 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-305">ID of the domain of this assembly.</span></span>|
|`BindingID`|`win:UInt64`|<span data-ttu-id="b3e47-306">어셈블리 바인딩을 고유하게 식별하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-306">ID that uniquely identifies the assembly binding.</span></span>|
|`AssemblyFlags`|`win:UInt32`|<span data-ttu-id="b3e47-307">0x1: 도메인 중립 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-307">0x1: Domain neutral assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-308">0x2: 동적 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-308">0x2: Dynamic assembly.</span></span><br /><br /> <span data-ttu-id="b3e47-309">0x4: 어셈블리에 네이티브 이미지 있음.</span><span class="sxs-lookup"><span data-stu-id="b3e47-309">0x4: Assembly has a native image.</span></span><br /><br /> <span data-ttu-id="b3e47-310">0x8: 수집 가능한 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="b3e47-310">0x8: Collectible assembly.</span></span>|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-311">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-311">Fully qualified assembly name.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-312">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-312">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="assemblyloadstart-event"></a><span data-ttu-id="b3e47-313">AssemblyLoadStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-313">AssemblyLoadStart event</span></span>

|<span data-ttu-id="b3e47-314">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-314">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-315">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-315">Event</span></span>|<span data-ttu-id="b3e47-316">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-316">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-317">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-317">`Binder` (0x4)</span></span>|`AssemblyLoadStart`|<span data-ttu-id="b3e47-318">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-318">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-319">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-319">Event</span></span>|<span data-ttu-id="b3e47-320">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-320">Event ID</span></span>|<span data-ttu-id="b3e47-321">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-321">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|<span data-ttu-id="b3e47-322">290</span><span class="sxs-lookup"><span data-stu-id="b3e47-322">290</span></span>|<span data-ttu-id="b3e47-323">어셈블리 로드가 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-323">An assembly load has been requested.</span></span>

|<span data-ttu-id="b3e47-324">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-324">Field name</span></span>|<span data-ttu-id="b3e47-325">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-325">Data type</span></span>|<span data-ttu-id="b3e47-326">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-326">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-327">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-327">Name of assembly name.</span></span>|
|`AssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-328">어셈블리 이름의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-328">Path of assembly name.</span></span>|
|`RequestingAssembly`|`win:UnicodeString`|<span data-ttu-id="b3e47-329">요청 ("부모") 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-329">Name of the requesting ("parent") assembly.</span></span>|
|`AssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-330">어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-330">Load context of the assembly.</span></span>|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-331">요청 ("부모") 어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-331">Load context of the requesting ("parent") assembly.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-332">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-332">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="assemblyloadstop-event"></a><span data-ttu-id="b3e47-333">AssemblyLoadStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-333">AssemblyLoadStop event</span></span>

|<span data-ttu-id="b3e47-334">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-334">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-335">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-335">Event</span></span>|<span data-ttu-id="b3e47-336">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-336">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-337">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-337">`Binder` (0x4)</span></span>|`AssemblyLoadStart`|<span data-ttu-id="b3e47-338">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-338">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-339">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-339">Event</span></span>|<span data-ttu-id="b3e47-340">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-340">Event ID</span></span>|<span data-ttu-id="b3e47-341">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-341">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|<span data-ttu-id="b3e47-342">291</span><span class="sxs-lookup"><span data-stu-id="b3e47-342">291</span></span>|<span data-ttu-id="b3e47-343">어셈블리 로드가 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-343">An assembly load has been requested.</span></span>

|<span data-ttu-id="b3e47-344">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-344">Field name</span></span>|<span data-ttu-id="b3e47-345">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-345">Data type</span></span>|<span data-ttu-id="b3e47-346">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-346">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-347">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-347">Name of assembly name.</span></span>|
|`AssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-348">어셈블리 이름의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-348">Path of assembly name.</span></span>|
|`RequestingAssembly`|`win:UnicodeString`|<span data-ttu-id="b3e47-349">요청 ("부모") 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-349">Name of the requesting ("parent") assembly.</span></span>|
|`AssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-350">어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-350">Load context of the assembly.</span></span>|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-351">요청 ("부모") 어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-351">Load context of the requesting ("parent") assembly.</span></span>|
|`Success`|`win:Boolean`|<span data-ttu-id="b3e47-352">어셈블리 로드에 성공 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-352">Whether the assembly load succeeded.</span></span>|
|`ResultAssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-353">로드 된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-353">The name of assembly that was loaded.</span></span>|
|`ResultAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-354">에서 로드 된 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-354">The path of the assembly that was loaded from.</span></span>|
|`Cached`|`win:UnicodeString`|<span data-ttu-id="b3e47-355">부하가 캐시 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-355">Whether the load was cached.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-356">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-356">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="resolutionattempted-event"></a><span data-ttu-id="b3e47-357">ResolutionAttempted 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-357">ResolutionAttempted event</span></span>

|<span data-ttu-id="b3e47-358">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-358">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-359">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-359">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-360">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-360">`Binder` (0x4)</span></span>|<span data-ttu-id="b3e47-361">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-361">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-362">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-362">Event</span></span>|<span data-ttu-id="b3e47-363">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-363">Event ID</span></span>|<span data-ttu-id="b3e47-364">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-364">Description</span></span>|
|-----------|--------------|-----------------|
|`ResolutionAttempted`|<span data-ttu-id="b3e47-365">292</span><span class="sxs-lookup"><span data-stu-id="b3e47-365">292</span></span>|<span data-ttu-id="b3e47-366">어셈블리 로드가 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-366">An assembly load has been requested.</span></span>

|<span data-ttu-id="b3e47-367">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-367">Field name</span></span>|<span data-ttu-id="b3e47-368">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-368">Data type</span></span>|<span data-ttu-id="b3e47-369">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-369">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-370">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-370">Name of assembly name.</span></span>|
|`Stage`|`win:UInt16`|<span data-ttu-id="b3e47-371">해결 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-371">The resolution stage.</span></span><br/><br/><span data-ttu-id="b3e47-372">0: 로드 중을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-372">0: Find in load.</span></span><br/><br/><span data-ttu-id="b3e47-373">1: 어셈블리 로드 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="b3e47-373">1: Assembly Load Context</span></span></br><br/><span data-ttu-id="b3e47-374">2: 응용 프로그램 어셈블리</span><span class="sxs-lookup"><span data-stu-id="b3e47-374">2: Application assemblies.</span></span><br/><br/><span data-ttu-id="b3e47-375">3: 기본 어셈블리 로드 컨텍스트 대체입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-375">3: Default assembly load context fallback.</span></span> <br/><br/><span data-ttu-id="b3e47-376">4: 위성 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-376">4: Resolve satellite assembly.</span></span> <br/><br/><span data-ttu-id="b3e47-377">5: 어셈블리 로드 컨텍스트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-377">5: Assembly load context resolving.</span></span><br/><br/><span data-ttu-id="b3e47-378">6: AppDomain 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-378">6: AppDomain assembly resolving.</span></span>
|`AssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-379">어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-379">Load context of the assembly.</span></span>|
|`Result`|`win:UInt16`|<span data-ttu-id="b3e47-380">확인 시도의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-380">The result of resolution attempt.</span></span><br/><br/><span data-ttu-id="b3e47-381">0: 성공</span><span class="sxs-lookup"><span data-stu-id="b3e47-381">0: Success</span></span><br/><br/><span data-ttu-id="b3e47-382">1: 어셈블리 NotFound</span><span class="sxs-lookup"><span data-stu-id="b3e47-382">1: Assembly NotFound</span></span><br/><br/><span data-ttu-id="b3e47-383">2: 호환 되지 않는 버전</span><span class="sxs-lookup"><span data-stu-id="b3e47-383">2: Incompatible Version</span></span><br/><br/><span data-ttu-id="b3e47-384">3: 어셈블리 이름이 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-384">3: Mismatched Assembly Name</span></span><br/><br/><span data-ttu-id="b3e47-385">4: 실패</span><span class="sxs-lookup"><span data-stu-id="b3e47-385">4: Failure</span></span><br/><br/><span data-ttu-id="b3e47-386">5: 예외</span><span class="sxs-lookup"><span data-stu-id="b3e47-386">5: Exception</span></span>|
|`ResultAssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-387">확인 된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-387">The name of assembly that was resolved.</span></span>|
|`ResultAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-388">에서 확인 된 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-388">The path of the assembly that was resolved from.</span></span>|
|`ErrorMessage`|`win:UnicodeString`|<span data-ttu-id="b3e47-389">예외가 있는 경우 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-389">Error message if there is an exception.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-390">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-390">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="assemblyloadcontextresolvinghandlerinvoked-event"></a><span data-ttu-id="b3e47-391">AssemblyLoadContextResolvingHandlerInvoked 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-391">AssemblyLoadContextResolvingHandlerInvoked event</span></span>

|<span data-ttu-id="b3e47-392">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-392">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-393">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-393">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-394">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-394">`Binder` (0x4)</span></span>|<span data-ttu-id="b3e47-395">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-395">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-396">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-396">Event</span></span>|<span data-ttu-id="b3e47-397">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-397">Event ID</span></span>|<span data-ttu-id="b3e47-398">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-398">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyLoadContextResolvingHandlerInvoked`|<span data-ttu-id="b3e47-399">293</span><span class="sxs-lookup"><span data-stu-id="b3e47-399">293</span></span>|<span data-ttu-id="b3e47-400">[Assemblyloadcontext입니다.](xref:System.Runtime.Loader.AssemblyLoadContext.Resolving) 처리기를 확인 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-400">An [AssemblyLoadContext.Resolving](xref:System.Runtime.Loader.AssemblyLoadContext.Resolving) handler has been invoked.</span></span>|

|<span data-ttu-id="b3e47-401">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-401">Field name</span></span>|<span data-ttu-id="b3e47-402">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-402">Data type</span></span>|<span data-ttu-id="b3e47-403">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-403">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-404">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-404">Name of assembly name.</span></span>|
|`HandlerName`|`win:UnicodeString`|<span data-ttu-id="b3e47-405">호출 된 처리기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-405">Name of the handler invoked.</span></span>|
|`AssemblyLoadContext`|`win:UnicodeString`|<span data-ttu-id="b3e47-406">어셈블리의 로드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-406">Load context of the assembly.</span></span>|
|`ResultAssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-407">확인 된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-407">The name of assembly that was resolved.</span></span>|
|`ResultAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-408">에서 확인 된 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-408">The path of the assembly that was resolved from.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-409">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-409">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="appdomainassemblyresolvehandlerinvoked-event"></a><span data-ttu-id="b3e47-410">AppDomainAssemblyResolveHandlerInvoked 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-410">AppDomainAssemblyResolveHandlerInvoked event</span></span>

|<span data-ttu-id="b3e47-411">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-411">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-412">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-412">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-413">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-413">`Binder` (0x4)</span></span>|<span data-ttu-id="b3e47-414">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-414">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-415">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-415">Event</span></span>|<span data-ttu-id="b3e47-416">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-416">Event ID</span></span>|<span data-ttu-id="b3e47-417">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-417">Description</span></span>|
|-----------|--------------|-----------------|
|`AppDomainAssemblyResolveHandlerInvoked`|<span data-ttu-id="b3e47-418">294</span><span class="sxs-lookup"><span data-stu-id="b3e47-418">294</span></span>|<span data-ttu-id="b3e47-419"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>처리기가 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-419">An <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> handler has been invoked.</span></span>|

|<span data-ttu-id="b3e47-420">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-420">Field name</span></span>|<span data-ttu-id="b3e47-421">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-421">Data type</span></span>|<span data-ttu-id="b3e47-422">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-422">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-423">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-423">Name of assembly name.</span></span>|
|`HandlerName`|`win:UnicodeString`|<span data-ttu-id="b3e47-424">호출 된 처리기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-424">Name of the handler invoked.</span></span>|
|`ResultAssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-425">확인 된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-425">The name of assembly that was resolved.</span></span>|
|`ResultAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-426">에서 확인 된 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-426">The path of the assembly that was resolved from.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-427">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-427">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="assemblyloadfromresolvehandlerinvoked-event"></a><span data-ttu-id="b3e47-428">AssemblyLoadFromResolveHandlerInvoked 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-428">AssemblyLoadFromResolveHandlerInvoked event</span></span>

|<span data-ttu-id="b3e47-429">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-429">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-430">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-430">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-431">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-431">`Binder` (0x4)</span></span>|<span data-ttu-id="b3e47-432">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-432">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-433">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-433">Event</span></span>|<span data-ttu-id="b3e47-434">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-434">Event ID</span></span>|<span data-ttu-id="b3e47-435">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-435">Description</span></span>|
|-----------|--------------|-----------------|
|`AssemblyLoadFromResolveHandlerInvoked`|<span data-ttu-id="b3e47-436">295</span><span class="sxs-lookup"><span data-stu-id="b3e47-436">295</span></span>|<span data-ttu-id="b3e47-437"><xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>처리기가 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-437">An <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> handler has been invoked.</span></span>|

|<span data-ttu-id="b3e47-438">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-438">Field name</span></span>|<span data-ttu-id="b3e47-439">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-439">Data type</span></span>|<span data-ttu-id="b3e47-440">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-440">Description</span></span>|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|<span data-ttu-id="b3e47-441">어셈블리 이름 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-441">Name of assembly name.</span></span>|
|`IsTrackedLoad`|`win:Boolean`|<span data-ttu-id="b3e47-442">어셈블리 로드를 추적할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-442">Whether the assembly load is tracked.</span></span>|
|`RequestingAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-443">요청 하는 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-443">The path of the requesting assembly.</span></span>|
|`ComputedRequestedAssemblyPath`|`win:UnicodeString`|<span data-ttu-id="b3e47-444">요청 된 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-444">The path of the assembly that was requested.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-445">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-445">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="knownpathprobed-event"></a><span data-ttu-id="b3e47-446">KnownPathProbed 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-446">KnownPathProbed event</span></span>

|<span data-ttu-id="b3e47-447">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b3e47-447">Keyword for raising the event</span></span>|<span data-ttu-id="b3e47-448">수준</span><span class="sxs-lookup"><span data-stu-id="b3e47-448">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="b3e47-449">`Binder` 0x4</span><span class="sxs-lookup"><span data-stu-id="b3e47-449">`Binder` (0x4)</span></span>|<span data-ttu-id="b3e47-450">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b3e47-450">Informational (4)</span></span>|

|<span data-ttu-id="b3e47-451">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3e47-451">Event</span></span>|<span data-ttu-id="b3e47-452">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b3e47-452">Event ID</span></span>|<span data-ttu-id="b3e47-453">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-453">Description</span></span>|
|-----------|--------------|-----------------|
|`KnownPathProbed`|<span data-ttu-id="b3e47-454">296</span><span class="sxs-lookup"><span data-stu-id="b3e47-454">296</span></span>|<span data-ttu-id="b3e47-455">어셈블리에 대해 알려진 경로를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-455">A known path was probed for an assembly.</span></span>|

|<span data-ttu-id="b3e47-456">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b3e47-456">Field Name</span></span>|<span data-ttu-id="b3e47-457">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e47-457">Data Type</span></span>|<span data-ttu-id="b3e47-458">Description</span><span class="sxs-lookup"><span data-stu-id="b3e47-458">Description</span></span>|
|----------------|---------------|-----------------|
|`FilePath`|`win:UnicodeString`|<span data-ttu-id="b3e47-459">경로를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-459">Path probed.</span></span>|
|`Source`|`win:UInt16`|<span data-ttu-id="b3e47-460">검색 된 경로의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-460">Source of the path probed.</span></span><br/><br/><span data-ttu-id="b3e47-461">0x0: 응용 프로그램 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-461">0x0:Application Assemblies.</span></span><br/><br/><span data-ttu-id="b3e47-462">0x1: 응용 프로그램 네이티브 이미지 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-462">0x1:App native image path.</span></span><br/><br/><span data-ttu-id="b3e47-463">0x2: 응용 프로그램 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-463">0x2:App path.</span></span></br><br/><span data-ttu-id="b3e47-464">0x3: 플랫폼 리소스 루트.</span><span class="sxs-lookup"><span data-stu-id="b3e47-464">0x3:Platform resource roots.</span></span><br/><br/><span data-ttu-id="b3e47-465">0x4: 위성 하위 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-465">0x4:Satellite Subdirectory.</span></span></br>|
|`Result`|`win:UInt32`|<span data-ttu-id="b3e47-466">프로브에 대 한 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-466">HRESULT for the probe.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="b3e47-467">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e47-467">Unique ID for the instance of CoreCLR.</span></span>|
