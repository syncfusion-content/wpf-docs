---
layout: post
title: WCF Service for Silverlight in WPF OLAPCommon control | Syncfusion
description: Create a wcf service for silverlight in Syncfusion Essential Studio WPF OLAPCommon control, its elements and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Create a WCF Service for Silverlight OLAP control



The following steps will define the adding of WCF Service to the Web project and configuring it with IOlapDataProvider:

1. Add WCF Service (from the installed templates) in to the Web project.
2. Inherit the newly added WCF service with IOlapDataProvider and explicitly implement the IOlapDataProvider. The connection to the database is done with the help of WCF service. The service has to be created and instantiated as described below:

   The WCF Service has to implement the IOlapDataProvider interface that requires the OlapDataProvider which can be instantiated by passing the connection string.

   The code snippet explains how to create OLAP WCF service in Web project:

   ~~~csharp

		    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]

		    [ServiceBehavior(IncludeExceptionDetailInFaults = true)]

		    public class OlapManager : IOlapDataProvider

		    { 

		        #region Private variables



		        private readonly OlapDataProvider _dataManager;



		        #endregion



		        #region Constructor

		        /// <summary>

		        /// Initializes a new instance of the <see cref="OlapManager"/> class.

		        /// </summary>

		        public OlapManager()

		        {

		            _dataManager = new OlapDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW");        

		} 

		        #endregion



		#region IOlapDataProvider Members





		public CellSet ExecuteOlapReportWithLevelTypeAll(OlapReport report, bool showLevelTypeAll)

		{

		CellSet cellSet = _dataManager.ExecuteOlapReportWithLevelTypeAll(report, showLevelTypeAll);

		_dataManager.DataProvider.CloseConnection();

		return cellSet;

		}



		/// <summary>

		/// Gets the MDX query.

		/// </summary>

		/// <param name="report">The report.</param>

		/// <returns></returns>

		public string GetMdxQuery(Syncfusion.OlapSilverlight.Reports.OlapReport report)

		{

		string mdxReturned = this._dataManager.GetMdxQuery(report);

		// Closing the Provider Connection

		this._dataManager.DataProvider.CloseConnection();

		return mdxReturned;

		}



		/// <summary>

		/// Executes the cell set.

		/// </summary>

		/// <param name="report">The report.</param>

		/// <returns></returns>

		public CellSet ExecuteOlapReport(OlapReport report)

		{

		CellSet cellSet = _dataManager.ExecuteOlapReport(report);

		_dataManager.DataProvider.CloseConnection();

		return cellSet;

		}



		/// <summary>

		/// Executes the MDX query.

		/// </summary>

		/// <param name="mdxQuery">The MDX query.</param>

		/// <returns></returns>

		public CellSet ExecuteMdxQuery(string mdxQuery)

		{

		CellSet cellSet = _dataManager.ExecuteMdxQuery(mdxQuery);

		_dataManager.DataProvider.CloseConnection();

		return cellSet;

		}



		/// <summary>

		/// Gets the cubes.

		/// </summary>

		/// <returns></returns>

		public CubeInfoCollection GetCubes()

		{

		CubeInfoCollection cubes = _dataManager.GetCubes();

		_dataManager.DataProvider.CloseConnection();

		return cubes;

		}



		/// <summary>

		/// Gets the cube schema.

		/// </summary>

		/// <param name="cubeName">Name of the cube.</param>

		/// <returns></returns>

		public CubeSchema GetCubeSchema(string cubeName)

		{

		CubeSchema cubeSchema = _dataManager.GetCubeSchema(cubeName);

		_dataManager.DataProvider.CloseConnection();

		return cubeSchema;

		}



		/// <summary>

		/// Gets the child members.

		/// </summary>

		/// <param name="memberUniqueName">Name of the member unique.</param>

		/// <param name="cubeName">Name of the cube.</param>

		/// <returns></returns>

		public MemberCollection GetChildMembers(string memberUniqueName, string cubeName)

		{

		MemberCollection childMembers = _dataManager.GetChildMembers(memberUniqueName, cubeName);

		_dataManager.DataProvider.CloseConnection();

		return childMembers;

		}



		/// <summary>

		/// Gets the level members.

		/// </summary>

		/// <param name="levelUniqueName">Name of the level unique.</param>

		/// <param name="cubeName">Name of the cube.</param>

		/// <returns></returns>

		public MemberCollection GetLevelMembers(string levelUniqueName, string cubeName)

		{

		MemberCollection levelMembers = _dataManager.GetLevelMembers(levelUniqueName, cubeName);

		_dataManager.DataProvider.CloseConnection();

		return levelMembers;

		}



		/// <summary>

		/// Executes the specified MDX query.

		/// </summary>

		/// <param name="mdxQuery">The MDX query.</param>

		/// <returns></returns>

		public object Execute(string mdxQuery)

		{

		var resultSet = this._dataManager.Execute(mdxQuery);

		// Closing the Provider Connection

		_dataManager.DataProvider.CloseConnection();

		return resultSet;

		}



		/// <summary>

		/// Executes the olap report with total count.

		/// </summary>

		/// <param name="report">The report.</param>

		/// <returns></returns>

		public Syncfusion.OlapSilverlight.Common.SerializableDictionary<string, object> ExecuteOlapReportWithTotalCount(OlapReport report)

		{

		Syncfusion.OlapSilverlight.Common.SerializableDictionary<string, object> dict = this._dataManager.ExecuteOlapReportWithTotalCount(report);

		// Closing the Provider Connection

		this._dataManager.DataProvider.CloseConnection();

		return dict;

		}



		#endregion

   ~~~

   ~~~vbnet

		<AspNetCompatibilityRequirements(RequirementsMode := AspNetCompatibilityRequirementsMode.Allowed)> _

		<ServiceBehavior(IncludeExceptionDetailInFaults := True)> _

		Public Class OlapManager 

		Implements IOlapDataProvider



		#Region "Member"

		Private ReadOnly _dataManager As OlapDataProvider

		#End Region





		#Region "Constructor"

		Public Sub New()

		_dataManager = New OlapDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW")

		End Sub

		#End Region



		#Region "IOlapDataProvider Members"



		Public Function ExecuteOlapReportWithLevelTypeAll(ByVal report As OlapReport, ByVal showLevelTypeAll As Boolean) As CellSet

		Dim cellSet As CellSet = _dataManager.ExecuteOlapReportWithLevelTypeAll(report, showLevelTypeAll)

		_dataManager.DataProvider.CloseConnection()

		Return cellSet

		End Function

		Public Function GetMdxQuery(ByVal report As Syncfusion.OlapSilverlight.Reports.OlapReport) As String

		Dim mdxReturned As String = Me._dataManager.GetMdxQuery(report)

		Me._dataManager.DataProvider.CloseConnection()

		Return mdxReturned

		End Function

		Public Function ExecuteOlapReport(ByVal report As OlapReport) As CellSet

		Dim cellSet As CellSet = _dataManager.ExecuteOlapReport(report)

		_dataManager.DataProvider.CloseConnection()

		Return cellSet

		End Function

		Public Function ExecuteMdxQuery(ByVal mdxQuery As String) As CellSet

		Dim cellSet As CellSet = _dataManager.ExecuteMdxQuery(mdxQuery)

		_dataManager.DataProvider.CloseConnection()

		Return cellSet

		End Function

		Public Function GetCubes() As CubeInfoCollection

		Dim cubes As CubeInfoCollection = _dataManager.GetCubes()

		_dataManager.DataProvider.CloseConnection()

		Return cubes

		End Function

		Public Function GetCubeSchema(ByVal cubeName As String) As CubeSchema

		Dim cubeSchema As CubeSchema = _dataManager.GetCubeSchema(cubeName)

		_dataManager.DataProvider.CloseConnection()

		Return cubeSchema

		End Function

		Public Function GetChildMembers(ByVal memberUniqueName As String, ByVal cubeName As String) As MemberCollection

		Dim childMembers As MemberCollection = _dataManager.GetChildMembers(memberUniqueName, cubeName)

		_dataManager.DataProvider.CloseConnection()

		Return childMembers

		End Function

		Public Function GetLevelMembers(ByVal levelUniqueName As String, ByVal cubeName As String) As MemberCollection

		Dim levelMembers As MemberCollection = _dataManager.GetLevelMembers(levelUniqueName, cubeName)

		_dataManager.DataProvider.CloseConnection()

		Return levelMembers

		End Function

		Public Function Execute(ByVal mdxQuery As String) As Object

		Dim resultSet As var = Me._dataManager.Execute(mdxQuery)

		_dataManager.DataProvider.CloseConnection()

		Return resultSet

		End Function

		Public Function ExecuteOlapReportWithTotalCount(ByVal report As OlapReport) As Syncfusion.OlapSilverlight.Common.SerializableDictionary(Of String, Object)

		Dim dict As Syncfusion.OlapSilverlight.Common.SerializableDictionary(Of String, Object) = Me._dataManager.ExecuteOlapReportWithTotalCount(report)

		Me._dataManager.DataProvider.CloseConnection()

		Return dict

		End Function

		#End Region

		#End Class

   ~~~

3. Include the custom binding and the service endpoint address in the Web.Config file.     




   ~~~xaml
   
		<!--Binding-->

		   <bindings>
		     <customBinding>
		       <binding name="binaryHttpBinding">
		        <binaryMessageEncoding/>
		        <httpTransport maxReceivedMessageSize="2147483647"/>
		       </binding>
		     </customBinding>
		   </bindings>

		   <!—Endpoint Address-->
		   <services>
		     <service name="SilverlightApplication1.Web.OlapManager" >
		       <endpoint address="binary" binding="customBinding" bindingConfiguration="binaryHttpBinding" contract="Syncfusion.OlapSilverlight.Manager.IOlapDataProvider">
		       </endpoint>
		     </service>
		   </services>


   ~~~
