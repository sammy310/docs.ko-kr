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
# <a name="apis-that-always-throw-exceptions-on-net-core"></a>.NET Core에서 항상 예외를 throw하는 API

다음 API는 모든 또는 일부 플랫폼의 .NET Core에서 <xref:System.PlatformNotSupportedException>를 throw합니다.

이 문서에서는 네임스페이스별로 영향을 받는 API 멤버를 구성합니다.

> [!NOTE]
>
> - 이 문서는 작성 중입니다. .NET Core에서 예외를 throw하는 API의 전체 목록이 아닙니다.
> - 이 문서에는 .NET Core에서 throw하는 이진 Serialization에 대한 명시적 인터페이스 구현이 포함되어 있지 않습니다. 자세한 내용은 [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)을 참조하세요.

## <a name="system"></a>시스템

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | 모두 |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | 모두 |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | 모두 |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | 모두 |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | 모두 |

## <a name="systemcodedomcompiler"></a>System.CodeDom.Compiler

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | 모두 |

## <a name="systemcollectionsspecialized"></a>System.Collections.Specialized

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | 모두 |

## <a name="systemconfiguration"></a>System.Configuration

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(모든 멤버) | 모두 |

## <a name="systemconsole"></a>System.Console

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Console.BufferHeight?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.BufferWidth?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.CursorSize?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.CursorVisible?displayProperty=nameWithType>(가져오기만) | Linux 및 macOS |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Console.Title?displayProperty=nameWithType>(가져오기만) | Linux 및 macOS |
| <xref:System.Console.WindowHeight?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.WindowLeft?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.WindowTop?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Console.WindowWidth?displayProperty=nameWithType>(설정만) | Linux 및 macOS |

## <a name="systemdatacommon"></a>System.Data.Common

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(<xref:System.NotSupportedException> throw) | 모두 |

## <a name="systemdiagnosticsprocess"></a>System.Diagnostics.Process

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(설정만) | Linux |
| <xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(설정만) | Linux |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | macOS |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(가져오기만) | macOS |
| <xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(설정만) | Linux 및 macOS |

## <a name="systemio"></a>System.IO

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |

## <a name="systemiopipes"></a>System.IO.Pipes

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(설정만) | Linux 및 macOS |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | Linux 및 macOS |

## <a name="systemmedia"></a>System.Media

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |

## <a name="systemnet"></a>System.Net

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |

## <a name="systemnetnetworkinformation"></a>System.Net.NetworkInformation

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | Windows(UWP) |

## <a name="systemnetsockets"></a>System.Net.Sockets

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | 모두 |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | 모두 |

## <a name="systemnetwebsockets"></a>System.Net.WebSockets

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | 모두 |

## <a name="systemreflection"></a>System.Reflection

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | 모두 |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | 모두 |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | 모두 |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | 모두 |

## <a name="systemruntimecompilerservices"></a>System.Runtime.CompilerServices

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | 모두 |

## <a name="systemruntimeinteropservices"></a>System.Runtime.InteropServices

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | 모두 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | 모두 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | 모두 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | 모두 |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | Linux 및 macOS |

## <a name="systemruntimeserialization"></a>System.Runtime.Serialization

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | 모두 |

## <a name="systemsecurity"></a>System.Security

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | 모두 |

## <a name="systemsecurityclaims"></a>System.Security.Claims

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | 모두 |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | 모두 |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |

## <a name="systemsecuritycryptography"></a>System.Security.Cryptography

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | Linux 및 macOS |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | 모두 |

## <a name="systemsecuritycryptographypkcs"></a>System.Security.Cryptography.Pkcs

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | 모두 |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | 모두 |

## <a name="systemsecuritycryptographyx509certificates"></a>System.Security.Cryptography.X509Certificates

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(설정만) | 모두 |

## <a name="systemsecurityauthenticationextendedprotection"></a>System.Security.Authentication.ExtendedProtection

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |

## <a name="systemsecuritypolicy"></a>System.Security.Policy

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |

## <a name="systemserviceprocessservicecontroller"></a>System.ServiceProcess.ServiceController

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | 모두 |

## <a name="systemtextregularexpressions"></a>System.Text.RegularExpressions

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | 모두 |

## <a name="systemthreading"></a>System.Threading

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 모두 |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | 모두 |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | 모두 |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | 모두 |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | 모두 |

## <a name="systemxml"></a>System.Xml

| 멤버 | throw되는 플랫폼 |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | 모두 |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | 모두 |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | 모두 |

## <a name="see-also"></a>참고 항목

- [.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 주요 변경](fx-core.md)
- [.NET Core의 이진 Serialization](../../standard/serialization/binary-serialization.md#net-core)
- [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md):
