---
description: '자세한 정보: Oracle 데이터 형식 매핑'
title: Oracle 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 1b5a130916a54049518b8b335fbf384d99035090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754370"
---
# <a name="oracle-data-type-mappings"></a>Oracle 데이터 형식 매핑

다음 표에는 Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.  
  
|Oracle 데이터 형식|OracleDataReader.GetValue에 의해 반환되는 .NET Framework 데이터 형식|OracleDataReader.GetOracleValue에 의해 반환되는 OracleClient 데이터 형식|설명|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte []**|<xref:System.Data.OracleClient.OracleBFile>||  
|**LO**|**Byte []**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**10진수**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **숫자** 데이터 형식에 대 한 별칭이 며에서 <xref:System.Data.OracleClient.OracleDataReader> 부동 소수점 값 대신 **Decimal** 을 반환 하도록 디자인 되었습니다 <xref:System.Data.OracleClient.OracleNumber> . .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTEGER**|**10진수**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **NUMBER (38)** 데이터 형식에 대 한 별칭이 며,는 <xref:System.Data.OracleClient.OracleDataReader> **Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> integer 값 대신를 반환 하도록 디자인 되었습니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**수많은**|**10진수**|<xref:System.Data.OracleClient.OracleNumber>|.NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**미처리**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** 데이터 형식은 개체에서 지원 되지 않습니다 <xref:System.Data.OracleClient.OracleDataReader> .|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**부호 없는 정수**|**Number**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **NUMBER (38)** 데이터 형식의 별칭이 며에서 <xref:System.Data.OracleClient.OracleDataReader> **Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> unsigned 정수 값 대신를 반환 하도록 디자인 되었습니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 다음 표에서는 Oracle 데이터 .NET Framework 형식과이를 매개 변수로 바인딩할 때 사용할 데이터 형식 (system.string 및)을 **보여 줍니다.** <xref:System.Data.OracleClient.OracleType>  
  
|Oracle 데이터 형식|매개 변수로 바인딩하는 DbType 열거형|매개 변수로 바인딩하는 OracleType 열거형|설명|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**목록은**|Oracle **에서는 bfile을** **bfile** 매개 변수로만 바인딩할 수 있습니다. Oracle에 대 한 .NET Data Provider **byte []** 또는 등의 **BFILE** 이 아닌 값을 바인딩하려는 경우이를 자동으로 생성 하지 않습니다 <xref:System.Data.OracleClient.OracleBinary> .|  
|**LO**||**Blob**|Oracle **에서는 blob를** **blob** 매개 변수로 바인딩할 수 있습니다. Oracle에 대 한 .NET Data Provider **byte []** 또는와 같은 **BLOB** 이 아닌 값을 바인딩하려는 경우이를 자동으로 생성 하지 않습니다 <xref:System.Data.OracleClient.OracleBinary> .|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle **에서는 clob을** **clob** 매개 변수로 바인딩할 수 있습니다. **System.string** 또는와 같은 **CLOB** 이 아닌 값을 바인딩하려는 경우에는 Oracle 용 .net Data Provider 자동으로 생성 하지 <xref:System.Data.OracleClient.OracleString> 않습니다.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 는 **system.object** <xref:System.Data.OracleClient.OracleType> 및를 확인 합니다.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 는 **system.object** <xref:System.Data.OracleClient.OracleType> 및를 확인 합니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**INTERVAL DAY TO SECOND**|**개체**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**이진**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle **에서는 nclob를** **nclob** 매개 변수로만 바인딩할 수 있습니다. Oracle의 .NET Data Provider는 **system.string** 또는와 같은 **NCLOB** 가 아닌 값을 바인딩하려는 경우 자동으로 생성 하지 <xref:System.Data.OracleClient.OracleString> 않습니다.|  
|**수많은**|**VarNumeric**|**Number**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**미처리**|**이진**|**원시**||  
|**REF CURSOR**||**커서**|자세한 내용은 [ORACLE REF cursor](oracle-ref-cursors.md)를 참조 하십시오.|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**부호 없는 정수**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 는 **system.object** <xref:System.Data.OracleClient.OracleType> 및를 확인 합니다.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 .NET Framework 개체의 속성에서 사용 되는 **Inputoutput**, **output** 및 **ReturnValue** **ParameterDirection** 값은 <xref:System.Data.OracleClient.OracleParameter.Value%2A> <xref:System.Data.OracleClient.OracleParameter> 입력 값이 Oracle 데이터 형식 (예: 또는)이 아닌 한 데이터 형식입니다 <xref:System.Data.OracleClient.OracleNumber> <xref:System.Data.OracleClient.OracleString> . **REF CURSOR**, **BFILE** 또는 **LOB** 데이터 형식에는 적용 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [Oracle 및 ADO.NET](oracle-and-adonet.md)
- [ADO.NET 개요](ado-net-overview.md)
