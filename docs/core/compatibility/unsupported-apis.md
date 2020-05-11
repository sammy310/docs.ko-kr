---
title: .NET Core에서 지원되지 않는 API
titleSuffix: ''
description: .NET Core에서 항상 예외를 throw하는 .NET Framework의 API를 알아봅니다.
ms.date: 12/23/2019
ms.openlocfilehash: 941e9149c7679afe4a888149108d0a9a28e5e7ab
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794600"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="9bb89-103">.NET Core에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="9bb89-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="9bb89-104">다음 API는 모든 또는 일부 플랫폼의 .NET Core에서 <xref:System.PlatformNotSupportedException>를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb89-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="9bb89-105">이 문서에서는 네임스페이스별로 영향을 받는 API 멤버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb89-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9bb89-106">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb89-106">This article is a work-in-progress.</span></span> <span data-ttu-id="9bb89-107">.NET Core에서 예외를 throw하는 API의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9bb89-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="9bb89-108">이 문서에는 .NET Core에서 throw하는 이진 Serialization에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb89-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="9bb89-109">자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb89-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="9bb89-110">시스템</span><span class="sxs-lookup"><span data-stu-id="9bb89-110">System</span></span>

| <span data-ttu-id="9bb89-111">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-111">Member</span></span> | <span data-ttu-id="9bb89-112">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-113">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-114">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="9bb89-115">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="9bb89-116">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-117">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="9bb89-118">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9bb89-119">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9bb89-120">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-121">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-122">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="9bb89-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="9bb89-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="9bb89-124">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-124">Member</span></span> | <span data-ttu-id="9bb89-125">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-126">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-127">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-128">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="9bb89-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="9bb89-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="9bb89-130">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-130">Member</span></span> | <span data-ttu-id="9bb89-131">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-132">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-133">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-134">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="9bb89-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="9bb89-135">System.Configuration</span></span>

| <span data-ttu-id="9bb89-136">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-136">Member</span></span> | <span data-ttu-id="9bb89-137">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bb89-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="9bb89-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="9bb89-139">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="9bb89-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="9bb89-140">System.Console</span></span>

| <span data-ttu-id="9bb89-141">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-141">Member</span></span> | <span data-ttu-id="9bb89-142">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="9bb89-143">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-143">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-145">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-145">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-147">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-147">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-149">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-149">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bb89-151">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-152">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-153">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-154">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-154">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-155"><xref:System.Console.Title?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bb89-156">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-156">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-158">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-158">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-160">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-160">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-162">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-162">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-164">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="9bb89-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="9bb89-165">System.Data.Common</span></span>

| <span data-ttu-id="9bb89-166">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-166">Member</span></span> | <span data-ttu-id="9bb89-167">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bb89-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw)</span><span class="sxs-lookup"><span data-stu-id="9bb89-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="9bb89-169">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="9bb89-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="9bb89-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="9bb89-171">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-171">Member</span></span> | <span data-ttu-id="9bb89-172">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9bb89-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-174">Linux</span><span class="sxs-lookup"><span data-stu-id="9bb89-174">Linux</span></span> |
| <span data-ttu-id="9bb89-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-176">Linux</span><span class="sxs-lookup"><span data-stu-id="9bb89-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="9bb89-177">macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="9bb89-178">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-179">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="9bb89-180">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="9bb89-181">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="9bb89-182">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="9bb89-183">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-183">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-185">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-185">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9bb89-187">macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-187">macOS</span></span> |
| <span data-ttu-id="9bb89-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-189">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="9bb89-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="9bb89-190">System.IO</span></span>

| <span data-ttu-id="9bb89-191">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-191">Member</span></span> | <span data-ttu-id="9bb89-192">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-193">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-194">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="9bb89-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="9bb89-195">System.IO.Pipes</span></span>

| <span data-ttu-id="9bb89-196">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-196">Member</span></span> | <span data-ttu-id="9bb89-197">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="9bb89-198">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="9bb89-199">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9bb89-200">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9bb89-201">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-201">Linux and macOS</span></span> |
| <span data-ttu-id="9bb89-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-203">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="9bb89-204">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="9bb89-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="9bb89-205">System.Media</span></span>

| <span data-ttu-id="9bb89-206">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-206">Member</span></span> | <span data-ttu-id="9bb89-207">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-208">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="9bb89-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="9bb89-209">System.Net</span></span>

| <span data-ttu-id="9bb89-210">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-210">Member</span></span> | <span data-ttu-id="9bb89-211">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-212">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-213">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-214">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-215">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-216">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-217">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-218">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-219">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-220">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-221">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-222">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="9bb89-223">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-224">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-225">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-226">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-227">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-228">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="9bb89-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="9bb89-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="9bb89-230">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-230">Member</span></span> | <span data-ttu-id="9bb89-231">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-232">Windows(UWP)</span><span class="sxs-lookup"><span data-stu-id="9bb89-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="9bb89-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="9bb89-233">System.Net.Sockets</span></span>

| <span data-ttu-id="9bb89-234">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-234">Member</span></span> | <span data-ttu-id="9bb89-235">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="9bb89-236">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-237">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="9bb89-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="9bb89-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="9bb89-239">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-239">Member</span></span> | <span data-ttu-id="9bb89-240">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="9bb89-241">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="9bb89-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="9bb89-242">System.Reflection</span></span>

| <span data-ttu-id="9bb89-243">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-243">Member</span></span> | <span data-ttu-id="9bb89-244">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-245">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-246">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-247">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-248">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="9bb89-249">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-250">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="9bb89-251">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="9bb89-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="9bb89-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="9bb89-253">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-253">Member</span></span> | <span data-ttu-id="9bb89-254">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="9bb89-255">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="9bb89-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="9bb89-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="9bb89-257">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-257">Member</span></span> | <span data-ttu-id="9bb89-258">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-259">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="9bb89-260">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-261">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-262">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-263">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-264">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-265">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="9bb89-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="9bb89-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="9bb89-267">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-267">Member</span></span> | <span data-ttu-id="9bb89-268">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="9bb89-269">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="9bb89-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="9bb89-270">System.Security</span></span>

| <span data-ttu-id="9bb89-271">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-271">Member</span></span> | <span data-ttu-id="9bb89-272">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="9bb89-273">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9bb89-274">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-275">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="9bb89-276">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9bb89-277">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="9bb89-278">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="9bb89-279">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="9bb89-280">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9bb89-281">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9bb89-282">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="9bb89-283">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-284">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="9bb89-285">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="9bb89-286">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="9bb89-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="9bb89-287">System.Security.Claims</span></span>

| <span data-ttu-id="9bb89-288">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-288">Member</span></span> | <span data-ttu-id="9bb89-289">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="9bb89-290">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-291">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="9bb89-292">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-293">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-294">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="9bb89-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="9bb89-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="9bb89-296">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-296">Member</span></span> | <span data-ttu-id="9bb89-297">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-298">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="9bb89-299">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="9bb89-300">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="9bb89-301">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="9bb89-302">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9bb89-303">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="9bb89-304">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="9bb89-305">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="9bb89-306">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="9bb89-307">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="9bb89-308">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="9bb89-309">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="9bb89-310">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9bb89-311">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bb89-312">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="9bb89-313">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-314">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-315">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-316">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-317">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bb89-318">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-319">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-320">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-321">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="9bb89-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-322">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-323">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9bb89-324">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-325">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="9bb89-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="9bb89-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="9bb89-327">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-327">Member</span></span> | <span data-ttu-id="9bb89-328">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="9bb89-329">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-330">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="9bb89-331">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="9bb89-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="9bb89-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="9bb89-333">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-333">Member</span></span> | <span data-ttu-id="9bb89-334">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-335">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-336">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-337">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-337">All</span></span> |
| <span data-ttu-id="9bb89-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="9bb89-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9bb89-339">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="9bb89-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="9bb89-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="9bb89-341">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-341">Member</span></span> | <span data-ttu-id="9bb89-342">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-343">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="9bb89-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="9bb89-344">System.Security.Policy</span></span>

| <span data-ttu-id="9bb89-345">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-345">Member</span></span> | <span data-ttu-id="9bb89-346">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-347">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="9bb89-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="9bb89-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="9bb89-349">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-349">Member</span></span> | <span data-ttu-id="9bb89-350">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9bb89-351">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="9bb89-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="9bb89-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="9bb89-353">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-353">Member</span></span> | <span data-ttu-id="9bb89-354">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-355">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="9bb89-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="9bb89-356">System.Threading</span></span>

| <span data-ttu-id="9bb89-357">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-357">Member</span></span> | <span data-ttu-id="9bb89-358">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-359">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-360">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="9bb89-361">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="9bb89-362">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="9bb89-363">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="9bb89-364">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="9bb89-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="9bb89-365">System.Xml</span></span>

| <span data-ttu-id="9bb89-366">멤버</span><span class="sxs-lookup"><span data-stu-id="9bb89-366">Member</span></span> | <span data-ttu-id="9bb89-367">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="9bb89-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-368">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-369">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9bb89-370">모두</span><span class="sxs-lookup"><span data-stu-id="9bb89-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="9bb89-371">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bb89-371">See also</span></span>

- [<span data-ttu-id="9bb89-372">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 주요 변경</span><span class="sxs-lookup"><span data-stu-id="9bb89-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="9bb89-373">.NET Core의 이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="9bb89-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- <span data-ttu-id="9bb89-374">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):</span><span class="sxs-lookup"><span data-stu-id="9bb89-374">[.NET portability analyzer](../../standard/analyzers/portability-analyzer.md)</span></span>
