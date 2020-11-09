---
title: .NET Core 및 .NET 5+에서 지원되지 않는 API
titleSuffix: ''
description: .NET Core 및 .NET 5.0 이상 버전에서 항상 예외를 throw하는 .NET API를 알아봅니다.
ms.date: 10/13/2020
ms.openlocfilehash: 51d73557a48910d9cb1c4d3cdced34dfe4d849d8
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329783"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="c5899-103">.NET Core 및 .NET 5+에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="c5899-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="c5899-104">다음 API는 플랫폼 전체 또는 하위 집합의 .NET 5.0 이상 버전(.NET Core의 모든 버전 포함)에서 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c5899-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="c5899-105">이 문서에서는 네임스페이스별로 영향을 받는 API를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5899-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c5899-106">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c5899-106">This article is a work-in-progress.</span></span> <span data-ttu-id="c5899-107">.NET 5+에서 예외를 throw하는 API의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c5899-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="c5899-108">이 문서에는 .NET 5+에서 throw하는 이진 직렬화에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5899-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="c5899-109">자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5899-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="c5899-110">시스템</span><span class="sxs-lookup"><span data-stu-id="c5899-110">System</span></span>

| <span data-ttu-id="c5899-111">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-111">Member</span></span> | <span data-ttu-id="c5899-112">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-113">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="c5899-114">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="c5899-115">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="c5899-116">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-117">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="c5899-118">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c5899-119">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c5899-120">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-121">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c5899-122">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="c5899-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="c5899-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="c5899-124">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-124">Member</span></span> | <span data-ttu-id="c5899-125">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-126">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-127">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-128">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="c5899-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="c5899-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="c5899-130">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-130">Member</span></span> | <span data-ttu-id="c5899-131">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-132">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-133">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c5899-134">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="c5899-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="c5899-135">System.Configuration</span></span>

| <span data-ttu-id="c5899-136">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-136">Member</span></span> | <span data-ttu-id="c5899-137">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c5899-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="c5899-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="c5899-139">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="c5899-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="c5899-140">System.Console</span></span>

| <span data-ttu-id="c5899-141">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-141">Member</span></span> | <span data-ttu-id="c5899-142">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="c5899-143">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-143">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-145">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-145">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-147">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-147">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-149">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-149">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="c5899-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c5899-151">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-152">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-153">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-154">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-154">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-155"><xref:System.Console.Title?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="c5899-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c5899-156">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-156">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-158">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-158">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-160">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-160">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-162">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-162">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-164">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="c5899-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="c5899-165">System.Data.Common</span></span>

| <span data-ttu-id="c5899-166">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-166">Member</span></span> | <span data-ttu-id="c5899-167">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c5899-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw)</span><span class="sxs-lookup"><span data-stu-id="c5899-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="c5899-169">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="c5899-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="c5899-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="c5899-171">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-171">Member</span></span> | <span data-ttu-id="c5899-172">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c5899-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-174">Linux</span><span class="sxs-lookup"><span data-stu-id="c5899-174">Linux</span></span> |
| <span data-ttu-id="c5899-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-176">Linux</span><span class="sxs-lookup"><span data-stu-id="c5899-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="c5899-177">macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="c5899-178">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-179">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="c5899-180">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="c5899-181">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="c5899-182">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="c5899-183">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-183">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-185">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-185">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="c5899-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c5899-187">macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-187">macOS</span></span> |
| <span data-ttu-id="c5899-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-189">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="c5899-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="c5899-190">System.IO</span></span>

| <span data-ttu-id="c5899-191">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-191">Member</span></span> | <span data-ttu-id="c5899-192">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-193">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-194">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="c5899-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="c5899-195">System.IO.Pipes</span></span>

| <span data-ttu-id="c5899-196">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-196">Member</span></span> | <span data-ttu-id="c5899-197">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="c5899-198">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="c5899-199">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c5899-200">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c5899-201">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-201">Linux and macOS</span></span> |
| <span data-ttu-id="c5899-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-203">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="c5899-204">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="c5899-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="c5899-205">System.Media</span></span>

| <span data-ttu-id="c5899-206">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-206">Member</span></span> | <span data-ttu-id="c5899-207">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-208">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="c5899-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="c5899-209">System.Net</span></span>

| <span data-ttu-id="c5899-210">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-210">Member</span></span> | <span data-ttu-id="c5899-211">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c5899-212">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c5899-213">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-214">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-215">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-216">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-217">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-218">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-219">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-220">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-221">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-222">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="c5899-223">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-224">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-225">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-226">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-227">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-228">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="c5899-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="c5899-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="c5899-230">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-230">Member</span></span> | <span data-ttu-id="c5899-231">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-232">Windows(UWP)</span><span class="sxs-lookup"><span data-stu-id="c5899-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="c5899-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="c5899-233">System.Net.Sockets</span></span>

| <span data-ttu-id="c5899-234">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-234">Member</span></span> | <span data-ttu-id="c5899-235">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="c5899-236">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="c5899-237">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="c5899-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="c5899-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="c5899-239">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-239">Member</span></span> | <span data-ttu-id="c5899-240">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="c5899-241">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="c5899-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="c5899-242">System.Reflection</span></span>

| <span data-ttu-id="c5899-243">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-243">Member</span></span> | <span data-ttu-id="c5899-244">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-245">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-246">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-247">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c5899-248">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="c5899-249">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-250">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="c5899-251">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="c5899-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="c5899-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="c5899-253">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-253">Member</span></span> | <span data-ttu-id="c5899-254">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="c5899-255">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="c5899-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="c5899-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="c5899-257">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-257">Member</span></span> | <span data-ttu-id="c5899-258">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c5899-259">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="c5899-260">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c5899-261">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c5899-262">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-263">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c5899-264">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c5899-265">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="c5899-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="c5899-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="c5899-267">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-267">Member</span></span> | <span data-ttu-id="c5899-268">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="c5899-269">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="c5899-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="c5899-270">System.Security</span></span>

| <span data-ttu-id="c5899-271">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-271">Member</span></span> | <span data-ttu-id="c5899-272">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="c5899-273">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c5899-274">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-275">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="c5899-276">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c5899-277">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="c5899-278">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="c5899-279">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="c5899-280">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c5899-281">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c5899-282">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="c5899-283">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c5899-284">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="c5899-285">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="c5899-286">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="c5899-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="c5899-287">System.Security.Claims</span></span>

| <span data-ttu-id="c5899-288">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-288">Member</span></span> | <span data-ttu-id="c5899-289">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-290">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-291">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="c5899-292">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-293">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-294">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="c5899-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="c5899-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="c5899-296">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-296">Member</span></span> | <span data-ttu-id="c5899-297">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-298">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="c5899-299">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="c5899-300">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="c5899-301">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="c5899-302">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c5899-303">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="c5899-304">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="c5899-305">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="c5899-306">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="c5899-307">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="c5899-308">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="c5899-309">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="c5899-310">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c5899-311">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c5899-312">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="c5899-313">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-314">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-315">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-316">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-317">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c5899-318">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-319">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-320">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-321">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="c5899-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-322">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-323">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c5899-324">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c5899-325">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="c5899-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="c5899-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="c5899-327">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-327">Member</span></span> | <span data-ttu-id="c5899-328">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="c5899-329">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="c5899-330">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="c5899-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="c5899-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="c5899-332">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-332">Member</span></span> | <span data-ttu-id="c5899-333">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-334">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-335">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-336">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-336">All</span></span> |
| <span data-ttu-id="c5899-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="c5899-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c5899-338">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="c5899-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="c5899-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="c5899-340">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-340">Member</span></span> | <span data-ttu-id="c5899-341">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-342">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="c5899-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="c5899-343">System.Security.Policy</span></span>

| <span data-ttu-id="c5899-344">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-344">Member</span></span> | <span data-ttu-id="c5899-345">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-346">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="c5899-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c5899-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="c5899-348">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-348">Member</span></span> | <span data-ttu-id="c5899-349">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c5899-350">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="c5899-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="c5899-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="c5899-352">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-352">Member</span></span> | <span data-ttu-id="c5899-353">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-354">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="c5899-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="c5899-355">System.Threading</span></span>

| <span data-ttu-id="c5899-356">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-356">Member</span></span> | <span data-ttu-id="c5899-357">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-358">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c5899-359">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="c5899-360">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="c5899-361">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="c5899-362">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="c5899-363">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="c5899-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c5899-364">System.Xml</span></span>

| <span data-ttu-id="c5899-365">멤버</span><span class="sxs-lookup"><span data-stu-id="c5899-365">Member</span></span> | <span data-ttu-id="c5899-366">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c5899-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c5899-367">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c5899-368">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c5899-369">모두</span><span class="sxs-lookup"><span data-stu-id="c5899-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="c5899-370">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5899-370">See also</span></span>

- [<span data-ttu-id="c5899-371">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="c5899-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="c5899-372">.NET Core의 이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="c5899-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- <span data-ttu-id="c5899-373">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):</span><span class="sxs-lookup"><span data-stu-id="c5899-373">[.NET portability analyzer](../../standard/analyzers/portability-analyzer.md)</span></span>
