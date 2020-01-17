---
title: .NET Core에서 지원되지 않는 API
description: .NET Core에서 항상 예외를 throw하는 .NET Framework의 API를 알아봅니다.
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901345"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="fc8e4-103">.NET Core에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="fc8e4-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="fc8e4-104">다음 API는 지정된 플랫폼의 .NET Core에서 실행될 때 항상 <xref:System.PlatformNotSupportedException>을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="fc8e4-105">이 문서에서는 네임스페이스별로 영향을 받는 API 멤버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fc8e4-106">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-106">This article is a work-in-progress.</span></span> <span data-ttu-id="fc8e4-107">.NET Core에서 예외를 throw하는 API의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="fc8e4-108">이 문서에는 .NET Core에서 throw하는 이진 Serialization에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="fc8e4-109">자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc8e4-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="fc8e4-110">시스템</span><span class="sxs-lookup"><span data-stu-id="fc8e4-110">System</span></span>

| <span data-ttu-id="fc8e4-111">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-111">Member</span></span> | <span data-ttu-id="fc8e4-112">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-113">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-114">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-115">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-116">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-117">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-118">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-119">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-120">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-121">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-122">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="fc8e4-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="fc8e4-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="fc8e4-124">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-124">Member</span></span> | <span data-ttu-id="fc8e4-125">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-126">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-127">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-128">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="fc8e4-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="fc8e4-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="fc8e4-130">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-130">Member</span></span> | <span data-ttu-id="fc8e4-131">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-132">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-133">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-134">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="fc8e4-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="fc8e4-135">System.Configuration</span></span>

| <span data-ttu-id="fc8e4-136">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-136">Member</span></span> | <span data-ttu-id="fc8e4-137">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="fc8e4-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="fc8e4-139">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="fc8e4-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="fc8e4-140">System.Console</span></span>

| <span data-ttu-id="fc8e4-141">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-141">Member</span></span> | <span data-ttu-id="fc8e4-142">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-143">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-143">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-145">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-145">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-147">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-147">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-149">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-149">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="fc8e4-151">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-152">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-153">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-154">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-154">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-155"><xref:System.Console.Title?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="fc8e4-156">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-156">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-158">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-158">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-160">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-160">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-162">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-162">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-164">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="fc8e4-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="fc8e4-165">System.Data.Common</span></span>

| <span data-ttu-id="fc8e4-166">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-166">Member</span></span> | <span data-ttu-id="fc8e4-167">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="fc8e4-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="fc8e4-169">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="fc8e4-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="fc8e4-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="fc8e4-171">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-171">Member</span></span> | <span data-ttu-id="fc8e4-172">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="fc8e4-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-174">Linux</span><span class="sxs-lookup"><span data-stu-id="fc8e4-174">Linux</span></span> |
| <span data-ttu-id="fc8e4-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-176">Linux</span><span class="sxs-lookup"><span data-stu-id="fc8e4-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-177">macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-178">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-179">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-180">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-181">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-182">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-183">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-183">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-185">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-185">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="fc8e4-187">macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-187">macOS</span></span> |
| <span data-ttu-id="fc8e4-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-189">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="fc8e4-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="fc8e4-190">System.IO</span></span>

| <span data-ttu-id="fc8e4-191">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-191">Member</span></span> | <span data-ttu-id="fc8e4-192">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-193">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-194">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="fc8e4-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="fc8e4-195">System.IO.Pipes</span></span>

| <span data-ttu-id="fc8e4-196">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-196">Member</span></span> | <span data-ttu-id="fc8e4-197">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-198">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-199">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-200">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-201">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-201">Linux and macOS</span></span> |
| <span data-ttu-id="fc8e4-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-203">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-204">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="fc8e4-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="fc8e4-205">System.Media</span></span>

| <span data-ttu-id="fc8e4-206">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-206">Member</span></span> | <span data-ttu-id="fc8e4-207">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-208">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="fc8e4-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="fc8e4-209">System.Net</span></span>

| <span data-ttu-id="fc8e4-210">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-210">Member</span></span> | <span data-ttu-id="fc8e4-211">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-212">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-213">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-214">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-215">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-216">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-217">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-218">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-219">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-220">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-221">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-222">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-223">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-224">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-225">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-226">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-227">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-228">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="fc8e4-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="fc8e4-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="fc8e4-230">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-230">Member</span></span> | <span data-ttu-id="fc8e4-231">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-232">Windows(UWP)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="fc8e4-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="fc8e4-233">System.Net.Sockets</span></span>

| <span data-ttu-id="fc8e4-234">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-234">Member</span></span> | <span data-ttu-id="fc8e4-235">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-236">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="fc8e4-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="fc8e4-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="fc8e4-238">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-238">Member</span></span> | <span data-ttu-id="fc8e4-239">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-240">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="fc8e4-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="fc8e4-241">System.Reflection</span></span>

| <span data-ttu-id="fc8e4-242">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-242">Member</span></span> | <span data-ttu-id="fc8e4-243">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-244">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-245">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-246">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-247">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-248">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-249">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-250">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="fc8e4-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="fc8e4-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="fc8e4-252">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-252">Member</span></span> | <span data-ttu-id="fc8e4-253">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-254">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="fc8e4-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="fc8e4-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="fc8e4-256">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-256">Member</span></span> | <span data-ttu-id="fc8e4-257">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-258">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-259">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-260">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-261">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-262">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-263">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-264">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="fc8e4-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="fc8e4-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="fc8e4-266">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-266">Member</span></span> | <span data-ttu-id="fc8e4-267">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-268">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="fc8e4-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="fc8e4-269">System.Security</span></span>

| <span data-ttu-id="fc8e4-270">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-270">Member</span></span> | <span data-ttu-id="fc8e4-271">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-272">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-273">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-274">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-275">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-276">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-277">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-278">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-279">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-280">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-281">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-282">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-283">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-284">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-285">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="fc8e4-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="fc8e4-286">System.Security.Claims</span></span>

| <span data-ttu-id="fc8e4-287">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-287">Member</span></span> | <span data-ttu-id="fc8e4-288">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-289">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-290">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-291">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-292">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-293">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="fc8e4-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="fc8e4-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="fc8e4-295">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-295">Member</span></span> | <span data-ttu-id="fc8e4-296">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-297">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-298">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-299">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-300">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-301">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-302">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-303">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-304">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-305">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-306">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-307">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-308">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-309">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-310">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-311">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-312">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-313">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-314">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-315">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-316">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-317">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-318">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-319">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-320">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-321">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="fc8e4-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-322">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-323">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-324">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-325">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="fc8e4-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="fc8e4-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="fc8e4-327">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-327">Member</span></span> | <span data-ttu-id="fc8e4-328">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-329">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-330">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-331">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="fc8e4-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="fc8e4-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="fc8e4-333">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-333">Member</span></span> | <span data-ttu-id="fc8e4-334">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-335">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-336">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-337">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-337">All</span></span> |
| <span data-ttu-id="fc8e4-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="fc8e4-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="fc8e4-339">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="fc8e4-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="fc8e4-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="fc8e4-341">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-341">Member</span></span> | <span data-ttu-id="fc8e4-342">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-343">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="fc8e4-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="fc8e4-344">System.Security.Policy</span></span>

| <span data-ttu-id="fc8e4-345">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-345">Member</span></span> | <span data-ttu-id="fc8e4-346">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-347">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="fc8e4-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="fc8e4-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="fc8e4-349">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-349">Member</span></span> | <span data-ttu-id="fc8e4-350">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-351">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="fc8e4-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="fc8e4-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="fc8e4-353">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-353">Member</span></span> | <span data-ttu-id="fc8e4-354">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-355">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="fc8e4-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="fc8e4-356">System.Threading</span></span>

| <span data-ttu-id="fc8e4-357">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-357">Member</span></span> | <span data-ttu-id="fc8e4-358">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-359">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-360">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-361">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-362">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-363">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-364">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="fc8e4-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="fc8e4-365">System.Xml</span></span>

| <span data-ttu-id="fc8e4-366">멤버</span><span class="sxs-lookup"><span data-stu-id="fc8e4-366">Member</span></span> | <span data-ttu-id="fc8e4-367">플랫폼</span><span class="sxs-lookup"><span data-stu-id="fc8e4-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-368">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-369">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="fc8e4-370">모두</span><span class="sxs-lookup"><span data-stu-id="fc8e4-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="fc8e4-371">참조</span><span class="sxs-lookup"><span data-stu-id="fc8e4-371">See also</span></span>

- [<span data-ttu-id="fc8e4-372">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 주요 변경</span><span class="sxs-lookup"><span data-stu-id="fc8e4-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="fc8e4-373">.NET Core의 이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="fc8e4-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- <span data-ttu-id="fc8e4-374">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):</span><span class="sxs-lookup"><span data-stu-id="fc8e4-374">[.NET portability analyzer](../../standard/analyzers/portability-analyzer.md)</span></span>
