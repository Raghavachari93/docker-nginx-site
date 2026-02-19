<h1>Static Website Deployment using Docker + Nginx</h1>

<p>
This project demonstrates how to deploy a static website in a production-style environment using
containers. It uses the official images from 
:contentReference[oaicite:0]{index=0}
and 
:contentReference[oaicite:1]{index=1}
to serve a frontend application.
</p>

<hr>

<h2>Project Overview</h2>
<ul>
<li>Containerize a static website</li>
<li>Serve frontend files through Nginx</li>
<li>Understand container image layering</li>
<li>Learn real-world frontend deployment workflow</li>
</ul>

<hr>

<h2>Goal</h2>
<p>Run the project and open it in your browser:</p>

<pre>http://localhost:8080</pre>

<p>You should see the deployed webpage running from inside a container.</p>

<hr>

<h2>Project Structure</h2>
<pre>
docker-nginx-site/
 ├── index.html
 └── Dockerfile
</pre>

<hr>

<h2>Prerequisites</h2>
<ul>
<li>Docker installed</li>
<li>Basic command line knowledge</li>
<li>Git installed</li>
</ul>

<hr>

<h2>Step 1 — Clone Repository</h2>
<pre>git clone https://github.com/Raghavachari93/docker-nginx-site.git
cd docker-nginx-site</pre>

<hr>

<h2>Step 2 — Build Docker Image</h2>
<p>Build the container image from the project directory:</p>

<pre>docker build -t nginx-static-site .</pre>

<p>Verify image:</p>
<pre>docker images</pre>

<hr>

<h2>Step 3 — Run Container</h2>

<pre>docker run -d -p 8080:80 --name nginx-container nginx-static-site</pre>

<ul>
<li><b>8080</b> → Host machine port</li>
<li><b>80</b> → Container web server port</li>
</ul>

<hr>

<h2>Step 4 — Access Website</h2>

<p>Open your browser and visit:</p>
<pre>http://localhost:8080</pre>

<hr>

<h2>Useful Debug Commands</h2>

<pre>
docker logs nginx-container
docker exec -it nginx-container sh
docker stop nginx-container
docker rm nginx-container
</pre>

<hr>

<h2>Concepts Covered</h2>

<table border="1" cellpadding="8" cellspacing="0">
<tr>
<th>Concept</th>
<th>Description</th>
</tr>
<tr>
<td>Official Images</td>
<td>Using trusted container images for reliability</td>
</tr>
<tr>
<td>Containerized Frontend</td>
<td>Serving web content through Nginx</td>
</tr>
<tr>
<td>Port Mapping</td>
<td>Connecting container ports to host system</td>
</tr>
<tr>
<td>Layer Caching</td>
<td>Understanding image build performance</td>
</tr>
</table>

<hr>

<h2>Optional — Live Editing Mode</h2>

<p>Instead of rebuilding the image every time you update files, you can mount a volume:</p>

<pre>
docker run -d -p 8080:80 \
-v $(pwd):/usr/share/nginx/html \
nginx:alpine
</pre>

<p>Now any file change instantly reflects in the browser.</p>

<hr>

<h2>Learning Outcome</h2>

<p>After completing this project you can:</p>
<ul>
<li>Deploy frontend apps inside containers</li>
<li>Understand production-style static hosting</li>
<li>Work with container networking and ports</li>
<li>Use container images efficiently</li>
</ul>

<hr>



<hr>

<h2>Author</h2>
<p>Maintained on 
:contentReference[oaicite:2]{index=2}
by <b>Raghavachari93</b></p>

<hr>

<h3 align="center">Congratulations — You’re deploying like a real DevOps Engineer!</h3>
