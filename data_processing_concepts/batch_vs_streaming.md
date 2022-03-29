<p align="center" style="background-color:"><img src="../assets/logo.jpeg"  width="400"></p><p align="center"><h2 style="color: #193967; text-align: center">
    Batch processing VS Streaming Processing
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>


### What is Batch Processing
Jobs that can run without end user interaction, or can be scheduled to run as resources permit, are called batch jobs.
Batch processing is for those frequently used programs that can be executed with minimal human interaction.

A program that reads a large file and generates a report, for example, is considered to be a batch job.


The term **batch job** originated in the days when punched cards contained the directions for a computer to follow when running one or more programs.
Multiple card decks representing multiple jobs would often be stacked on top of one another in the hopper of a card reader, and be run in batches.

### What is stream processing

Stream processing is the practice of taking action on a series of data at the time the data is created. Historically, 
data practitioners used “real-time processing” to talk generally about data that was processed as frequently as necessary for a particular use case.
But with the advent and adoption of
stream processing technologies and frameworks, coupled with decreasing prices for RAM, “stream processing” is used in a more specific manner.


Stream processing often entails multiple tasks on the incoming series of data (the “data stream”), which can be performed serially, in parallel, or
both. This workflow is referred to as a stream processing pipeline, which includes the generation of the stream data, 
the processing of the data, and the delivery of the data to a final location.



### DIfferences between Stream and batch processing
<table>
    <thead>
        <tr>
            <th>Batch Processing</th>
            <th>Stream Processing</th>
       </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data is collected over time	</td>
            <td>Data streams continuously</td>
        </tr>  
        <tr>
            <td>Once data is collected, it’s sent for processing</td>
            <td>Data is processed piece-by-piece</td>
        </tr>
        <tr>
            <td>Batch processing is lengthy and is meant for large quantities of information that aren’t time-sensitive</td>
            <td>Stream processing is fast and is meant for information that’s needed immediately</td>
        </tr>
    </tbody>
</table>

### Batch processing vs. stream processing
The distinction between batch processing and stream processing is one of the most fundamental principles within the big data world.
There is no official definition of these two terms, but when most people use them, they mean the following:
- Under the batch processing model, a set of data is collected over time, then fed into an analytics system. In other words, you collect a batch of information,
  then send it in for processing.
- Under the streaming model, data is fed into analytics tools piece-by-piece. The processing is usually done in real time.



### Reading material
- <a href="https://hazelcast.com/lp/stream-processing-instant-insight-into-data-as-it-flows/?utm_campaign=Stream+Processing&utm_source=google&utm_medium=cpc&utm_term=stream%20processing&utm_content=adgroupid:61010613760%20creative:525642232014%20matchtype:e%20network:g%20device:c%20position:%20placement:&adgroupid=61010613760&creativeid=525642232014&campaignid=1530472473&gclid=CjwKCAjw55-HBhAHEiwARMCszkYYOAWRb61lpboM2aa_TS0qws6cNYmtbxYN0b-IgDJAFmf0s-h4-xoCL7IQAvD_BwE">Stream Processing</a>


### Visual Material 
- <a href="https://www.youtube.com/watch?v=tNWetmyztII" >Batch</a>
- <a href="https://www.youtube.com/watch?v=A3Mvy8WMk04" >Batch vs Streaming </a>
