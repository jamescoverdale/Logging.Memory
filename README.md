# Logging.Memory

NuGet package [Logging.Memory](https://www.nuget.org/packages/Logging.Memory/)

## How to use

### 1. Enable Logging in Startup.cs

        public void Configure(IApplicationBuilder app,
            IHostingEnvironment env,
            ILoggerFactory loggerFactory)
        {
            ...
            loggerFactory.MinimumLevel = LogLevel.Debug;
            loggerFactory.AddMemory();
            ...
        }
        
or via ILoggingBuilder

        builder.Logging.AddMemory(LogLevel.Debug);

### 2. Now you can get log from static List everywhere
     
    var logList = MemoryLogger.LogList;

Since v2.0.0 you can get log for concrete LogLevel:

    var warnLog = MemoryLogger.GetLog(LogLevel.Warning);

