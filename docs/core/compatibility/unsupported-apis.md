---
title: .NET Core 및 .NET 5+에서 지원되지 않는 API
titleSuffix: ''
description: .NET Core 및 .NET 5.0 이상 버전에서 항상 예외를 throw하는 .NET API를 알아봅니다.
ms.date: 10/13/2020
ms.openlocfilehash: 0164ebff51de82d548a02f9fde754c1052a9c2b5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159341"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="20883-103">.NET Core 및 .NET 5+에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="20883-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="20883-104">다음 API는 플랫폼 전체 또는 하위 집합의 .NET 5.0 이상 버전(.NET Core의 모든 버전 포함)에서 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="20883-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="20883-105">이 문서에서는 네임스페이스별로 영향을 받는 API를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20883-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="20883-106">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="20883-106">This article is a work-in-progress.</span></span> <span data-ttu-id="20883-107">.NET 5+에서 예외를 throw하는 API의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="20883-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="20883-108">이 문서에는 .NET 5+에서 throw하는 이진 직렬화에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20883-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="20883-109">자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20883-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="20883-110">시스템</span><span class="sxs-lookup"><span data-stu-id="20883-110">System</span></span>

| <span data-ttu-id="20883-111">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-111">Member</span></span> | <span data-ttu-id="20883-112">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-113">모두</span><span class="sxs-lookup"><span data-stu-id="20883-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="20883-114">모두</span><span class="sxs-lookup"><span data-stu-id="20883-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="20883-115">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="20883-116">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-117">모두</span><span class="sxs-lookup"><span data-stu-id="20883-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="20883-118">모두</span><span class="sxs-lookup"><span data-stu-id="20883-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="20883-119">모두</span><span class="sxs-lookup"><span data-stu-id="20883-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="20883-120">모두</span><span class="sxs-lookup"><span data-stu-id="20883-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-121">모두</span><span class="sxs-lookup"><span data-stu-id="20883-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="20883-122">모두</span><span class="sxs-lookup"><span data-stu-id="20883-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="20883-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="20883-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="20883-124">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-124">Member</span></span> | <span data-ttu-id="20883-125">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-126">모두</span><span class="sxs-lookup"><span data-stu-id="20883-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-127">모두</span><span class="sxs-lookup"><span data-stu-id="20883-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-128">모두</span><span class="sxs-lookup"><span data-stu-id="20883-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="20883-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="20883-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="20883-130">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-130">Member</span></span> | <span data-ttu-id="20883-131">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-132">모두</span><span class="sxs-lookup"><span data-stu-id="20883-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-133">모두</span><span class="sxs-lookup"><span data-stu-id="20883-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="20883-134">모두</span><span class="sxs-lookup"><span data-stu-id="20883-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="20883-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="20883-135">System.Configuration</span></span>

| <span data-ttu-id="20883-136">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-136">Member</span></span> | <span data-ttu-id="20883-137">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="20883-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="20883-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="20883-139">모두</span><span class="sxs-lookup"><span data-stu-id="20883-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="20883-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="20883-140">System.Console</span></span>

| <span data-ttu-id="20883-141">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-141">Member</span></span> | <span data-ttu-id="20883-142">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="20883-143">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-143">Linux and macOS</span></span> |
| <span data-ttu-id="20883-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-145">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-145">Linux and macOS</span></span> |
| <span data-ttu-id="20883-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-147">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-147">Linux and macOS</span></span> |
| <span data-ttu-id="20883-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-149">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-149">Linux and macOS</span></span> |
| <span data-ttu-id="20883-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="20883-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="20883-151">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-152">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-153">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-154">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-154">Linux and macOS</span></span> |
| <span data-ttu-id="20883-155"><xref:System.Console.Title?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="20883-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="20883-156">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-156">Linux and macOS</span></span> |
| <span data-ttu-id="20883-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-158">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-158">Linux and macOS</span></span> |
| <span data-ttu-id="20883-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-160">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-160">Linux and macOS</span></span> |
| <span data-ttu-id="20883-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-162">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-162">Linux and macOS</span></span> |
| <span data-ttu-id="20883-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-164">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="20883-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="20883-165">System.Data.Common</span></span>

| <span data-ttu-id="20883-166">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-166">Member</span></span> | <span data-ttu-id="20883-167">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="20883-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw)</span><span class="sxs-lookup"><span data-stu-id="20883-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="20883-169">모두</span><span class="sxs-lookup"><span data-stu-id="20883-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="20883-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="20883-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="20883-171">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-171">Member</span></span> | <span data-ttu-id="20883-172">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="20883-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-174">Linux</span><span class="sxs-lookup"><span data-stu-id="20883-174">Linux</span></span> |
| <span data-ttu-id="20883-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-176">Linux</span><span class="sxs-lookup"><span data-stu-id="20883-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="20883-177">macOS</span><span class="sxs-lookup"><span data-stu-id="20883-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="20883-178">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-179">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="20883-180">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="20883-181">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="20883-182">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="20883-183">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-183">Linux and macOS</span></span> |
| <span data-ttu-id="20883-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-185">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-185">Linux and macOS</span></span> |
| <span data-ttu-id="20883-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="20883-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="20883-187">macOS</span><span class="sxs-lookup"><span data-stu-id="20883-187">macOS</span></span> |
| <span data-ttu-id="20883-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-189">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="20883-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="20883-190">System.IO</span></span>

| <span data-ttu-id="20883-191">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-191">Member</span></span> | <span data-ttu-id="20883-192">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-193">모두</span><span class="sxs-lookup"><span data-stu-id="20883-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-194">모두</span><span class="sxs-lookup"><span data-stu-id="20883-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="20883-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="20883-195">System.IO.Pipes</span></span>

| <span data-ttu-id="20883-196">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-196">Member</span></span> | <span data-ttu-id="20883-197">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="20883-198">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="20883-199">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="20883-200">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="20883-201">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-201">Linux and macOS</span></span> |
| <span data-ttu-id="20883-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-203">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="20883-204">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="20883-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="20883-205">System.Media</span></span>

| <span data-ttu-id="20883-206">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-206">Member</span></span> | <span data-ttu-id="20883-207">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-208">모두</span><span class="sxs-lookup"><span data-stu-id="20883-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="20883-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="20883-209">System.Net</span></span>

| <span data-ttu-id="20883-210">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-210">Member</span></span> | <span data-ttu-id="20883-211">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="20883-212">모두</span><span class="sxs-lookup"><span data-stu-id="20883-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="20883-213">모두</span><span class="sxs-lookup"><span data-stu-id="20883-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-214">모두</span><span class="sxs-lookup"><span data-stu-id="20883-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-215">모두</span><span class="sxs-lookup"><span data-stu-id="20883-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-216">모두</span><span class="sxs-lookup"><span data-stu-id="20883-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-217">모두</span><span class="sxs-lookup"><span data-stu-id="20883-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-218">모두</span><span class="sxs-lookup"><span data-stu-id="20883-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-219">모두</span><span class="sxs-lookup"><span data-stu-id="20883-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-220">모두</span><span class="sxs-lookup"><span data-stu-id="20883-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-221">모두</span><span class="sxs-lookup"><span data-stu-id="20883-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-222">모두</span><span class="sxs-lookup"><span data-stu-id="20883-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="20883-223">모두</span><span class="sxs-lookup"><span data-stu-id="20883-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-224">모두</span><span class="sxs-lookup"><span data-stu-id="20883-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-225">모두</span><span class="sxs-lookup"><span data-stu-id="20883-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-226">모두</span><span class="sxs-lookup"><span data-stu-id="20883-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-227">모두</span><span class="sxs-lookup"><span data-stu-id="20883-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-228">모두</span><span class="sxs-lookup"><span data-stu-id="20883-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="20883-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="20883-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="20883-230">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-230">Member</span></span> | <span data-ttu-id="20883-231">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-232">Windows(UWP)</span><span class="sxs-lookup"><span data-stu-id="20883-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="20883-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="20883-233">System.Net.Sockets</span></span>

| <span data-ttu-id="20883-234">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-234">Member</span></span> | <span data-ttu-id="20883-235">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="20883-236">모두</span><span class="sxs-lookup"><span data-stu-id="20883-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="20883-237">모두</span><span class="sxs-lookup"><span data-stu-id="20883-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="20883-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="20883-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="20883-239">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-239">Member</span></span> | <span data-ttu-id="20883-240">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="20883-241">모두</span><span class="sxs-lookup"><span data-stu-id="20883-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="20883-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="20883-242">System.Reflection</span></span>

| <span data-ttu-id="20883-243">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-243">Member</span></span> | <span data-ttu-id="20883-244">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-245">모두</span><span class="sxs-lookup"><span data-stu-id="20883-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-246">모두</span><span class="sxs-lookup"><span data-stu-id="20883-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-247">모두</span><span class="sxs-lookup"><span data-stu-id="20883-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="20883-248">모두</span><span class="sxs-lookup"><span data-stu-id="20883-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="20883-249">모두</span><span class="sxs-lookup"><span data-stu-id="20883-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-250">모두</span><span class="sxs-lookup"><span data-stu-id="20883-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="20883-251">모두</span><span class="sxs-lookup"><span data-stu-id="20883-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="20883-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="20883-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="20883-253">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-253">Member</span></span> | <span data-ttu-id="20883-254">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="20883-255">모두</span><span class="sxs-lookup"><span data-stu-id="20883-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="20883-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="20883-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="20883-257">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-257">Member</span></span> | <span data-ttu-id="20883-258">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="20883-259">모두</span><span class="sxs-lookup"><span data-stu-id="20883-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="20883-260">모두</span><span class="sxs-lookup"><span data-stu-id="20883-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="20883-261">모두</span><span class="sxs-lookup"><span data-stu-id="20883-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="20883-262">모두</span><span class="sxs-lookup"><span data-stu-id="20883-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-263">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="20883-264">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="20883-265">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="20883-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="20883-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="20883-267">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-267">Member</span></span> | <span data-ttu-id="20883-268">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="20883-269">모두</span><span class="sxs-lookup"><span data-stu-id="20883-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="20883-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="20883-270">System.Security</span></span>

| <span data-ttu-id="20883-271">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-271">Member</span></span> | <span data-ttu-id="20883-272">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="20883-273">모두</span><span class="sxs-lookup"><span data-stu-id="20883-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="20883-274">모두</span><span class="sxs-lookup"><span data-stu-id="20883-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-275">모두</span><span class="sxs-lookup"><span data-stu-id="20883-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="20883-276">모두</span><span class="sxs-lookup"><span data-stu-id="20883-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="20883-277">모두</span><span class="sxs-lookup"><span data-stu-id="20883-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="20883-278">모두</span><span class="sxs-lookup"><span data-stu-id="20883-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="20883-279">모두</span><span class="sxs-lookup"><span data-stu-id="20883-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="20883-280">모두</span><span class="sxs-lookup"><span data-stu-id="20883-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="20883-281">모두</span><span class="sxs-lookup"><span data-stu-id="20883-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="20883-282">모두</span><span class="sxs-lookup"><span data-stu-id="20883-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="20883-283">모두</span><span class="sxs-lookup"><span data-stu-id="20883-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="20883-284">모두</span><span class="sxs-lookup"><span data-stu-id="20883-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="20883-285">모두</span><span class="sxs-lookup"><span data-stu-id="20883-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="20883-286">모두</span><span class="sxs-lookup"><span data-stu-id="20883-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="20883-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="20883-287">System.Security.Claims</span></span>

| <span data-ttu-id="20883-288">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-288">Member</span></span> | <span data-ttu-id="20883-289">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="20883-290">모두</span><span class="sxs-lookup"><span data-stu-id="20883-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-291">모두</span><span class="sxs-lookup"><span data-stu-id="20883-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="20883-292">모두</span><span class="sxs-lookup"><span data-stu-id="20883-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-293">모두</span><span class="sxs-lookup"><span data-stu-id="20883-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-294">모두</span><span class="sxs-lookup"><span data-stu-id="20883-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="20883-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="20883-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="20883-296">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-296">Member</span></span> | <span data-ttu-id="20883-297">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-298">모두</span><span class="sxs-lookup"><span data-stu-id="20883-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="20883-299">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="20883-300">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="20883-301">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="20883-302">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="20883-303">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="20883-304">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="20883-305">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="20883-306">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="20883-307">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="20883-308">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="20883-309">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="20883-310">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="20883-311">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="20883-312">모두</span><span class="sxs-lookup"><span data-stu-id="20883-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="20883-313">모두</span><span class="sxs-lookup"><span data-stu-id="20883-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-314">모두</span><span class="sxs-lookup"><span data-stu-id="20883-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-315">모두</span><span class="sxs-lookup"><span data-stu-id="20883-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-316">모두</span><span class="sxs-lookup"><span data-stu-id="20883-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-317">모두</span><span class="sxs-lookup"><span data-stu-id="20883-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="20883-318">모두</span><span class="sxs-lookup"><span data-stu-id="20883-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-319">모두</span><span class="sxs-lookup"><span data-stu-id="20883-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-320">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-321">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="20883-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-322">모두</span><span class="sxs-lookup"><span data-stu-id="20883-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-323">모두</span><span class="sxs-lookup"><span data-stu-id="20883-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="20883-324">모두</span><span class="sxs-lookup"><span data-stu-id="20883-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="20883-325">모두</span><span class="sxs-lookup"><span data-stu-id="20883-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="20883-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="20883-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="20883-327">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-327">Member</span></span> | <span data-ttu-id="20883-328">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="20883-329">모두</span><span class="sxs-lookup"><span data-stu-id="20883-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="20883-330">모두</span><span class="sxs-lookup"><span data-stu-id="20883-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="20883-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="20883-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="20883-332">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-332">Member</span></span> | <span data-ttu-id="20883-333">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-334">모두</span><span class="sxs-lookup"><span data-stu-id="20883-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-335">모두</span><span class="sxs-lookup"><span data-stu-id="20883-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-336">모두</span><span class="sxs-lookup"><span data-stu-id="20883-336">All</span></span> |
| <span data-ttu-id="20883-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="20883-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="20883-338">모두</span><span class="sxs-lookup"><span data-stu-id="20883-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="20883-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="20883-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="20883-340">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-340">Member</span></span> | <span data-ttu-id="20883-341">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-342">모두</span><span class="sxs-lookup"><span data-stu-id="20883-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="20883-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="20883-343">System.Security.Policy</span></span>

| <span data-ttu-id="20883-344">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-344">Member</span></span> | <span data-ttu-id="20883-345">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-346">모두</span><span class="sxs-lookup"><span data-stu-id="20883-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="20883-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="20883-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="20883-348">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-348">Member</span></span> | <span data-ttu-id="20883-349">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="20883-350">모두</span><span class="sxs-lookup"><span data-stu-id="20883-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="20883-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="20883-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="20883-352">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-352">Member</span></span> | <span data-ttu-id="20883-353">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-354">모두</span><span class="sxs-lookup"><span data-stu-id="20883-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="20883-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="20883-355">System.Threading</span></span>

| <span data-ttu-id="20883-356">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-356">Member</span></span> | <span data-ttu-id="20883-357">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-358">모두</span><span class="sxs-lookup"><span data-stu-id="20883-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="20883-359">모두</span><span class="sxs-lookup"><span data-stu-id="20883-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="20883-360">모두</span><span class="sxs-lookup"><span data-stu-id="20883-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="20883-361">모두</span><span class="sxs-lookup"><span data-stu-id="20883-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="20883-362">모두</span><span class="sxs-lookup"><span data-stu-id="20883-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="20883-363">모두</span><span class="sxs-lookup"><span data-stu-id="20883-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="20883-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="20883-364">System.Xml</span></span>

| <span data-ttu-id="20883-365">멤버</span><span class="sxs-lookup"><span data-stu-id="20883-365">Member</span></span> | <span data-ttu-id="20883-366">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="20883-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="20883-367">모두</span><span class="sxs-lookup"><span data-stu-id="20883-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="20883-368">모두</span><span class="sxs-lookup"><span data-stu-id="20883-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="20883-369">모두</span><span class="sxs-lookup"><span data-stu-id="20883-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="20883-370">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20883-370">See also</span></span>

- [<span data-ttu-id="20883-371">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="20883-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="20883-372">.NET Core의 이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="20883-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- <span data-ttu-id="20883-373">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):</span><span class="sxs-lookup"><span data-stu-id="20883-373">[.NET portability analyzer](../../standard/analyzers/portability-analyzer.md)</span></span>
