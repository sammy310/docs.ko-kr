---
title: .NET Core 및 .NET 5+에서 지원되지 않는 API
titleSuffix: ''
description: .NET Core 및 .NET 5 이상 버전에서 항상 예외를 throw하는 .NET API를 알아봅니다.
ms.date: 10/13/2020
ms.openlocfilehash: b0dc425bf5f7d8f2a44f51ffe75ffcb0c8a5a7ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256259"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="41757-103">.NET Core 및 .NET 5+에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="41757-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="41757-104">다음 API는 플랫폼 전체 또는 하위 세트의 .NET 5 이상 버전(.NET Core의 모든 버전 포함)에서 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="41757-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="41757-105">이 문서에서는 네임스페이스별로 영향을 받는 API를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="41757-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="41757-106">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="41757-106">This article is a work-in-progress.</span></span> <span data-ttu-id="41757-107">.NET 5+에서 예외를 throw하는 API의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="41757-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="41757-108">이 문서에는 .NET 5+에서 throw하는 이진 직렬화에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41757-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="41757-109">자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41757-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="41757-110">시스템</span><span class="sxs-lookup"><span data-stu-id="41757-110">System</span></span>

| <span data-ttu-id="41757-111">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-111">Member</span></span> | <span data-ttu-id="41757-112">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-113">모두</span><span class="sxs-lookup"><span data-stu-id="41757-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="41757-114">모두</span><span class="sxs-lookup"><span data-stu-id="41757-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="41757-115">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="41757-116">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-117">모두</span><span class="sxs-lookup"><span data-stu-id="41757-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="41757-118">모두</span><span class="sxs-lookup"><span data-stu-id="41757-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="41757-119">모두</span><span class="sxs-lookup"><span data-stu-id="41757-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="41757-120">모두</span><span class="sxs-lookup"><span data-stu-id="41757-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-121">모두</span><span class="sxs-lookup"><span data-stu-id="41757-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="41757-122">모두</span><span class="sxs-lookup"><span data-stu-id="41757-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="41757-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="41757-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="41757-124">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-124">Member</span></span> | <span data-ttu-id="41757-125">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-126">모두</span><span class="sxs-lookup"><span data-stu-id="41757-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-127">모두</span><span class="sxs-lookup"><span data-stu-id="41757-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-128">모두</span><span class="sxs-lookup"><span data-stu-id="41757-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="41757-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="41757-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="41757-130">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-130">Member</span></span> | <span data-ttu-id="41757-131">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-132">모두</span><span class="sxs-lookup"><span data-stu-id="41757-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-133">모두</span><span class="sxs-lookup"><span data-stu-id="41757-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="41757-134">모두</span><span class="sxs-lookup"><span data-stu-id="41757-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="41757-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="41757-135">System.Configuration</span></span>

| <span data-ttu-id="41757-136">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-136">Member</span></span> | <span data-ttu-id="41757-137">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="41757-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="41757-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="41757-139">모두</span><span class="sxs-lookup"><span data-stu-id="41757-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="41757-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="41757-140">System.Console</span></span>

| <span data-ttu-id="41757-141">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-141">Member</span></span> | <span data-ttu-id="41757-142">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="41757-143">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-143">Linux and macOS</span></span> |
| <span data-ttu-id="41757-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-145">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-145">Linux and macOS</span></span> |
| <span data-ttu-id="41757-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-147">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-147">Linux and macOS</span></span> |
| <span data-ttu-id="41757-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-149">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-149">Linux and macOS</span></span> |
| <span data-ttu-id="41757-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="41757-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="41757-151">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-152">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-153">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-154">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-154">Linux and macOS</span></span> |
| <span data-ttu-id="41757-155"><xref:System.Console.Title?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="41757-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="41757-156">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-156">Linux and macOS</span></span> |
| <span data-ttu-id="41757-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-158">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-158">Linux and macOS</span></span> |
| <span data-ttu-id="41757-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-160">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-160">Linux and macOS</span></span> |
| <span data-ttu-id="41757-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-162">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-162">Linux and macOS</span></span> |
| <span data-ttu-id="41757-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-164">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="41757-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="41757-165">System.Data.Common</span></span>

| <span data-ttu-id="41757-166">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-166">Member</span></span> | <span data-ttu-id="41757-167">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="41757-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw)</span><span class="sxs-lookup"><span data-stu-id="41757-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="41757-169">모두</span><span class="sxs-lookup"><span data-stu-id="41757-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="41757-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="41757-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="41757-171">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-171">Member</span></span> | <span data-ttu-id="41757-172">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="41757-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-174">Linux</span><span class="sxs-lookup"><span data-stu-id="41757-174">Linux</span></span> |
| <span data-ttu-id="41757-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-176">Linux</span><span class="sxs-lookup"><span data-stu-id="41757-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="41757-177">macOS</span><span class="sxs-lookup"><span data-stu-id="41757-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="41757-178">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-179">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-180">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="41757-181">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="41757-182">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="41757-183">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-183">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="41757-184">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-184">Linux and macOS</span></span> |
| <span data-ttu-id="41757-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-186">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-186">Linux and macOS</span></span> |
| <span data-ttu-id="41757-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만)</span><span class="sxs-lookup"><span data-stu-id="41757-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="41757-188">macOS</span><span class="sxs-lookup"><span data-stu-id="41757-188">macOS</span></span> |
| <span data-ttu-id="41757-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-190">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-190">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="41757-191">System.IO</span><span class="sxs-lookup"><span data-stu-id="41757-191">System.IO</span></span>

| <span data-ttu-id="41757-192">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-192">Member</span></span> | <span data-ttu-id="41757-193">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-193">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-194">모두</span><span class="sxs-lookup"><span data-stu-id="41757-194">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-195">모두</span><span class="sxs-lookup"><span data-stu-id="41757-195">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="41757-196">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="41757-196">System.IO.Pipes</span></span>

| <span data-ttu-id="41757-197">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-197">Member</span></span> | <span data-ttu-id="41757-198">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-198">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="41757-199">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="41757-200">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="41757-201">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-201">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="41757-202">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-202">Linux and macOS</span></span> |
| <span data-ttu-id="41757-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-204">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-204">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="41757-205">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-205">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="41757-206">System.Media</span><span class="sxs-lookup"><span data-stu-id="41757-206">System.Media</span></span>

| <span data-ttu-id="41757-207">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-207">Member</span></span> | <span data-ttu-id="41757-208">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-208">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-209">모두</span><span class="sxs-lookup"><span data-stu-id="41757-209">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="41757-210">System.Net</span><span class="sxs-lookup"><span data-stu-id="41757-210">System.Net</span></span>

| <span data-ttu-id="41757-211">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-211">Member</span></span> | <span data-ttu-id="41757-212">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-212">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="41757-213">모두</span><span class="sxs-lookup"><span data-stu-id="41757-213">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="41757-214">모두</span><span class="sxs-lookup"><span data-stu-id="41757-214">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-215">모두</span><span class="sxs-lookup"><span data-stu-id="41757-215">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-216">모두</span><span class="sxs-lookup"><span data-stu-id="41757-216">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-217">모두</span><span class="sxs-lookup"><span data-stu-id="41757-217">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-218">모두</span><span class="sxs-lookup"><span data-stu-id="41757-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-219">모두</span><span class="sxs-lookup"><span data-stu-id="41757-219">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-220">모두</span><span class="sxs-lookup"><span data-stu-id="41757-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-221">모두</span><span class="sxs-lookup"><span data-stu-id="41757-221">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-222">모두</span><span class="sxs-lookup"><span data-stu-id="41757-222">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-223">모두</span><span class="sxs-lookup"><span data-stu-id="41757-223">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="41757-224">모두</span><span class="sxs-lookup"><span data-stu-id="41757-224">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-225">모두</span><span class="sxs-lookup"><span data-stu-id="41757-225">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-226">모두</span><span class="sxs-lookup"><span data-stu-id="41757-226">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-227">모두</span><span class="sxs-lookup"><span data-stu-id="41757-227">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-228">모두</span><span class="sxs-lookup"><span data-stu-id="41757-228">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-229">모두</span><span class="sxs-lookup"><span data-stu-id="41757-229">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="41757-230">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="41757-230">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="41757-231">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-231">Member</span></span> | <span data-ttu-id="41757-232">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-232">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-233">Windows(UWP)</span><span class="sxs-lookup"><span data-stu-id="41757-233">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="41757-234">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="41757-234">System.Net.Sockets</span></span>

| <span data-ttu-id="41757-235">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-235">Member</span></span> | <span data-ttu-id="41757-236">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-236">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="41757-237">모두</span><span class="sxs-lookup"><span data-stu-id="41757-237">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="41757-238">모두</span><span class="sxs-lookup"><span data-stu-id="41757-238">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="41757-239">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="41757-239">System.Net.WebSockets</span></span>

| <span data-ttu-id="41757-240">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-240">Member</span></span> | <span data-ttu-id="41757-241">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-241">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="41757-242">모두</span><span class="sxs-lookup"><span data-stu-id="41757-242">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="41757-243">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="41757-243">System.Reflection</span></span>

| <span data-ttu-id="41757-244">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-244">Member</span></span> | <span data-ttu-id="41757-245">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-245">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-246">모두</span><span class="sxs-lookup"><span data-stu-id="41757-246">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-247">모두</span><span class="sxs-lookup"><span data-stu-id="41757-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-248">모두</span><span class="sxs-lookup"><span data-stu-id="41757-248">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="41757-249">모두</span><span class="sxs-lookup"><span data-stu-id="41757-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="41757-250">모두</span><span class="sxs-lookup"><span data-stu-id="41757-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-251">모두</span><span class="sxs-lookup"><span data-stu-id="41757-251">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="41757-252">모두</span><span class="sxs-lookup"><span data-stu-id="41757-252">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="41757-253">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="41757-253">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="41757-254">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-254">Member</span></span> | <span data-ttu-id="41757-255">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-255">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="41757-256">모두</span><span class="sxs-lookup"><span data-stu-id="41757-256">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="41757-257">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="41757-257">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="41757-258">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-258">Member</span></span> | <span data-ttu-id="41757-259">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-259">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="41757-260">모두</span><span class="sxs-lookup"><span data-stu-id="41757-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="41757-261">모두</span><span class="sxs-lookup"><span data-stu-id="41757-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="41757-262">모두</span><span class="sxs-lookup"><span data-stu-id="41757-262">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="41757-263">모두</span><span class="sxs-lookup"><span data-stu-id="41757-263">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-264">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="41757-265">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-265">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="41757-266">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-266">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="41757-267">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="41757-267">System.Runtime.Serialization</span></span>

| <span data-ttu-id="41757-268">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-268">Member</span></span> | <span data-ttu-id="41757-269">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-269">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="41757-270">모두</span><span class="sxs-lookup"><span data-stu-id="41757-270">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="41757-271">System.Security</span><span class="sxs-lookup"><span data-stu-id="41757-271">System.Security</span></span>

| <span data-ttu-id="41757-272">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-272">Member</span></span> | <span data-ttu-id="41757-273">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-273">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="41757-274">모두</span><span class="sxs-lookup"><span data-stu-id="41757-274">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="41757-275">모두</span><span class="sxs-lookup"><span data-stu-id="41757-275">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-276">모두</span><span class="sxs-lookup"><span data-stu-id="41757-276">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="41757-277">모두</span><span class="sxs-lookup"><span data-stu-id="41757-277">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="41757-278">모두</span><span class="sxs-lookup"><span data-stu-id="41757-278">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="41757-279">모두</span><span class="sxs-lookup"><span data-stu-id="41757-279">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="41757-280">모두</span><span class="sxs-lookup"><span data-stu-id="41757-280">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="41757-281">모두</span><span class="sxs-lookup"><span data-stu-id="41757-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="41757-282">모두</span><span class="sxs-lookup"><span data-stu-id="41757-282">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="41757-283">모두</span><span class="sxs-lookup"><span data-stu-id="41757-283">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="41757-284">모두</span><span class="sxs-lookup"><span data-stu-id="41757-284">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="41757-285">모두</span><span class="sxs-lookup"><span data-stu-id="41757-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="41757-286">모두</span><span class="sxs-lookup"><span data-stu-id="41757-286">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="41757-287">모두</span><span class="sxs-lookup"><span data-stu-id="41757-287">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="41757-288">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="41757-288">System.Security.Claims</span></span>

| <span data-ttu-id="41757-289">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-289">Member</span></span> | <span data-ttu-id="41757-290">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-290">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-291">모두</span><span class="sxs-lookup"><span data-stu-id="41757-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-292">모두</span><span class="sxs-lookup"><span data-stu-id="41757-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="41757-293">모두</span><span class="sxs-lookup"><span data-stu-id="41757-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-294">모두</span><span class="sxs-lookup"><span data-stu-id="41757-294">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-295">모두</span><span class="sxs-lookup"><span data-stu-id="41757-295">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="41757-296">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="41757-296">System.Security.Cryptography</span></span>

| <span data-ttu-id="41757-297">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-297">Member</span></span> | <span data-ttu-id="41757-298">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-298">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-299">모두</span><span class="sxs-lookup"><span data-stu-id="41757-299">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="41757-300">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="41757-301">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="41757-302">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="41757-303">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="41757-304">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="41757-305">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="41757-306">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="41757-307">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="41757-308">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="41757-309">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="41757-310">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="41757-311">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="41757-312">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-312">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="41757-313">모두</span><span class="sxs-lookup"><span data-stu-id="41757-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="41757-314">모두</span><span class="sxs-lookup"><span data-stu-id="41757-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-315">모두</span><span class="sxs-lookup"><span data-stu-id="41757-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-316">모두</span><span class="sxs-lookup"><span data-stu-id="41757-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-317">모두</span><span class="sxs-lookup"><span data-stu-id="41757-317">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-318">모두</span><span class="sxs-lookup"><span data-stu-id="41757-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="41757-319">모두</span><span class="sxs-lookup"><span data-stu-id="41757-319">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-320">모두</span><span class="sxs-lookup"><span data-stu-id="41757-320">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-321">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-322">Linux 및 macOS</span><span class="sxs-lookup"><span data-stu-id="41757-322">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-323">모두</span><span class="sxs-lookup"><span data-stu-id="41757-323">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-324">모두</span><span class="sxs-lookup"><span data-stu-id="41757-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="41757-325">모두</span><span class="sxs-lookup"><span data-stu-id="41757-325">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="41757-326">모두</span><span class="sxs-lookup"><span data-stu-id="41757-326">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="41757-327">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="41757-327">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="41757-328">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-328">Member</span></span> | <span data-ttu-id="41757-329">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-329">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="41757-330">모두</span><span class="sxs-lookup"><span data-stu-id="41757-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="41757-331">모두</span><span class="sxs-lookup"><span data-stu-id="41757-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="41757-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="41757-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="41757-333">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-333">Member</span></span> | <span data-ttu-id="41757-334">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-335">모두</span><span class="sxs-lookup"><span data-stu-id="41757-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-336">모두</span><span class="sxs-lookup"><span data-stu-id="41757-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-337">모두</span><span class="sxs-lookup"><span data-stu-id="41757-337">All</span></span> |
| <span data-ttu-id="41757-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만)</span><span class="sxs-lookup"><span data-stu-id="41757-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="41757-339">모두</span><span class="sxs-lookup"><span data-stu-id="41757-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="41757-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="41757-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="41757-341">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-341">Member</span></span> | <span data-ttu-id="41757-342">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-343">모두</span><span class="sxs-lookup"><span data-stu-id="41757-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="41757-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="41757-344">System.Security.Policy</span></span>

| <span data-ttu-id="41757-345">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-345">Member</span></span> | <span data-ttu-id="41757-346">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-347">모두</span><span class="sxs-lookup"><span data-stu-id="41757-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="41757-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="41757-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="41757-349">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-349">Member</span></span> | <span data-ttu-id="41757-350">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="41757-351">모두</span><span class="sxs-lookup"><span data-stu-id="41757-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="41757-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="41757-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="41757-353">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-353">Member</span></span> | <span data-ttu-id="41757-354">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-355">모두</span><span class="sxs-lookup"><span data-stu-id="41757-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="41757-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="41757-356">System.Threading</span></span>

| <span data-ttu-id="41757-357">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-357">Member</span></span> | <span data-ttu-id="41757-358">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-359">모두</span><span class="sxs-lookup"><span data-stu-id="41757-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="41757-360">모두</span><span class="sxs-lookup"><span data-stu-id="41757-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="41757-361">모두</span><span class="sxs-lookup"><span data-stu-id="41757-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="41757-362">모두</span><span class="sxs-lookup"><span data-stu-id="41757-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="41757-363">모두</span><span class="sxs-lookup"><span data-stu-id="41757-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="41757-364">모두</span><span class="sxs-lookup"><span data-stu-id="41757-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="41757-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="41757-365">System.Xml</span></span>

| <span data-ttu-id="41757-366">멤버</span><span class="sxs-lookup"><span data-stu-id="41757-366">Member</span></span> | <span data-ttu-id="41757-367">throw되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41757-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="41757-368">모두</span><span class="sxs-lookup"><span data-stu-id="41757-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="41757-369">모두</span><span class="sxs-lookup"><span data-stu-id="41757-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="41757-370">모두</span><span class="sxs-lookup"><span data-stu-id="41757-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="41757-371">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41757-371">See also</span></span>

- [<span data-ttu-id="41757-372">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="41757-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="41757-373">.NET Core의 이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="41757-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- <span data-ttu-id="41757-374">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):</span><span class="sxs-lookup"><span data-stu-id="41757-374">[.NET portability analyzer](../../standard/analyzers/portability-analyzer.md)</span></span>
