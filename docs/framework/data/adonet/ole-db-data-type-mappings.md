---
title: OLE DB 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: a5c4b7264b9f8abb842fff3295d53ed8ab626671
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584526"
---
# <a name="ole-db-data-type-mappings"></a>OLE DB 데이터 형식 매핑
다음 표에서 데이터 형식에 대 한.NET Framework 형식 유추는.NET Framework Data Provider for OLE DB 및 ADO에서에서 (<xref:System.Data.OleDb>). 또한 이 표에는 <xref:System.Data.OleDb.OleDbDataReader>의 형식화된 접근자 메서드도 나열되어 있습니다.  
  
|ADO 형식|OLE DB 형식|.NET Framework 형식|.NET framework 형식화 된 접근자|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boolean|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|문자열|GetString()|  
|adChapter|DBTYPE_HCHAPTER|`DataReader`를 통해 지원됩니다. 참조 [DataReader를 사용 하 여 데이터를 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)합니다.|GetValue()|  
|adChar|DBTYPE_STR|문자열|GetString()|  
|adCurrency|DBTYPE_CY|Decimal|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal|GetDecimal()|  
|adDouble|DBTYPE_R8|Double|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|개체|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|개체|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|개체|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|개체|GetValue()|  
|adWChar|DBTYPE_WSTR|문자열|GetString()|  
|adUserDefined|DBTYPE_UDT|지원되지 않음||  
|adVarNumeric|DBTYPE_VARNUMERIC|지원되지 않음||  
  
 \* OLE DB 형식에 대 한 `DBTYPE_IUNKNOWN` 고 `DBTYPE_IDISPATCH`, 개체 참조는 포인터의 마샬링된 표현입니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
